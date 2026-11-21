# Implementazione: modelli non lineari

[:material-file-pdf-box: Dispensa (PDF)](pdf/dispensa-modellazione-pnl.pdf) · [:material-presentation: Slide del capitolo (PDF)](pdf/slide-03-python-gurobi.pdf)

I comandi generali di `gurobipy` (costruire, far girare, leggere la soluzione) sono in
[Modellazione PL, «Implementazione: modelli lineari»](https://fabiofurini.github.io/modellazione-pl/solver-lp/)
e nella [guida al solver](https://github.com/fabiofurini/modellazione-pl/blob/main/GUIDA_GUROBI.md).
Qui solo ciò che è proprio dei modelli non lineari.

**Un solver solo: anche gli NLP generali si risolvono con Gurobi** (dalla
versione 12), con la stessa sintassi e la stessa checklist dei modelli lineari di Modellazione PL.
Funzioni non lineari come vincoli funzionali su variabili ausiliarie — `addGenConstrLog`,
`addGenConstrExp`, `addGenConstrPow` con `m.Params.FuncNonlinear = 1` — e termini bilineari
con `m.Params.NonConvex = 2`: l'ottimo resta **globale certificato**. Esempi nel laboratorio:
budget pubblicitario (`log`), pricing a elasticità costante (`Pow` + bilineare), code M/M/1
(vincolo bilineare `w·(mu - lam) = 1`), Weber (vincoli conici `dx² + dy² ≤ d²`, un QCP
convesso). Per le analisi marginali stringere `MIPGap`, `FeasibilityTol` e `OptimalityTol`
a `1e-9`; riformulare per evitare quantità minuscole (es. `q·p^eps ≤ A` invece di
`q ≤ A·p^(-eps)`).


## Obiettivi quadratici

Gli obiettivi **quadratici** (Markowitz, SVM, smoothing, minimi quadrati) si scrivono in modo
naturale, come prodotti di variabili o di espressioni lineari:

```python
m.setObjective(x @ Q @ x, GRB.MINIMIZE)                  # forma matriciale (numpy)
m.setObjective(gp.quicksum(q[i,j]*x[i]*x[j] for i in I for j in I), GRB.MINIMIZE)
m.Params.NonConvex = 2      # solo per QP non convessi (es. pricing p*q)
```

Se $\boldsymbol Q \succeq 0$ il QP è convesso e non serve nessun parametro; con
`NonConvex = 2` Gurobi risolve all'ottimo globale anche i QP non convessi. Se `Pi` non è
disponibile (vincoli quadratici o funzionali) si usa `m.Params.QCPDual = 1` per i vincoli
quadratici, altrimenti la verifica per perturbazione.

## Come si scrivono

```python
m.Params.FuncNonlinear = 1     # funzioni trattate in modo esatto (globale)
z = m.addVar(lb=-GRB.INFINITY)
m.addGenConstrLog(g, z)        # z = log(g);  anche Exp, Pow, Sin, ...
m.addQConstr(w * v == 1)       # termini bilineari: servono NonConvex = 2
```

Due accorgimenti pratici, entrambi usati negli script del corso:

- **tolleranze**: per analisi marginali accurate (differenze tra due ottimi
  vicini) stringere `MIPGap`, `FeasibilityTol` e `OptimalityTol` a `1e-9`;
- **scalatura**: riformulare per evitare quantità minuscole — ad esempio
  `q ≤ A·p^(-eps)` si scrive `q·r ≤ A` con `r = p^eps`, che tiene i numeri in un
  range sano.

## I moltiplicatori nei modelli non lineari

Per QP/NLP convessi i moltiplicatori (`Pi` sui vincoli lineari, condizioni KKT in generale)
hanno la stessa lettura marginale dei prezzi ombra. Verifica numerica consigliata nel corso: perturbare il termine noto di ε e ricontrollare che
`nuovo_ottimo ≈ vecchio_ottimo + Pi·ε`.


## I moltiplicatori nei QP convessi

Nei QP convessi con vincoli lineari l'attributo `Pi` di ogni vincolo è il
moltiplicatore KKT; per i vincoli quadratici serve `m.Params.QCPDual = 1` (attributo
`QCPi`). A differenza degli LP il moltiplicatore è esatto solo al margine: la verifica
per perturbazione si fa con un $\varepsilon$ piccolo (esempio nel capitolo
[Produzione con smoothing quadratico](produzione-quadratica.md)).

## Perché un solver solo

Stessa sintassi, stessa checklist di interpretazione e — soprattutto — ottimo
**globale certificato** anche nei problemi non convessi: con un solver locale ogni
risultato andrebbe accompagnato dalla domanda «è solo un ottimo locale?». I
problemi convessi con sola struttura quadratica o conica (vincoli come
`dx² + dy² ≤ d²`) non richiedono nulla di speciale.
