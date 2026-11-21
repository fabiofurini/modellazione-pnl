# Teoria: ottimizzazione non lineare

[:material-file-pdf-box: Dispensa (PDF)](pdf/dispensa-modellazione-pnl.pdf) · [:material-presentation: Slide del capitolo (PDF)](pdf/slide-02-richiami.pdf)

!!! nota "Prerequisiti"

    - Dal modulo *Ottimizzazione convessa*, [Capitolo 3 «Funzioni convesse e concave»](https://fabiofurini.github.io/ottimizzazione-convessa/preliminari/03-funzioni-convesse-concave/): funzioni convesse e concave e la loro caratterizzazione al secondo ordine.

    - Dal modulo *Ottimizzazione convessa*, [Capitolo 4 «Funzioni quadratiche»](https://fabiofurini.github.io/ottimizzazione-convessa/preliminari/04-funzioni-quadratiche/): le funzioni quadratiche e le matrici semidefinite positive.

    - Dal modulo *Modellazione PL*, [Capitolo 2 «Richiami: programmazione lineare e analisi di sensitività»](https://fabiofurini.github.io/modellazione-pl/teoria-lp/): la dualità della PL, gli scarti complementari e i prezzi ombra.

!!! chiave "Obiettivi"

    Alla fine di questo capitolo sarai in grado di:

    - riconoscere un problema convesso e usare il fatto che ogni minimo locale è globale;

    - decidere dalla matrice $\boldsymbol Q$ se un QP è convesso;

    - scrivere le condizioni KKT di un problema e usarle per verificare una soluzione;

    - leggere i moltiplicatori come prezzi ombra e stimarli per perturbazione.

I richiami di teoria del corso: convessità, programmazione quadratica e
condizioni KKT — l'estensione non lineare della teoria degli LP, richiamata in
[Modellazione PL](https://fabiofurini.github.io/modellazione-pl/teoria-lp/) insieme al
protocollo di sensitività. Insiemi e funzioni convesse sono trattati nel corso
[Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/).

## Convessità e programmazione quadratica

Un **QP** ha obiettivo $\tfrac12 \boldsymbol x' \boldsymbol Q\, \boldsymbol x +
\boldsymbol c' \boldsymbol x$ e vincoli lineari; è convesso se e solo se
$\boldsymbol Q \succeq 0$. In un problema convesso ogni minimo locale è globale:
l'ottimalità si può *certificare*.

!!! example "Un QP 2×2, svolto per intero"
    Obiettivo quadratico separabile e un vincolo di soglia sulla somma:

    $$
    \begin{array}{r r@{\;}c@{\;}r c r l}
    \min & x_1^2 & + & 2\,x_2^2 & & & \\
    \text{soggetto a} & x_1 & + & x_2 & \ge & 6 & \\
     & x_1, & & x_2 & \ge & 0 &
    \end{array}
    $$

    $\boldsymbol Q = \mathrm{diag}(2, 4) \succ 0$: convesso, ottimo globale.
    **Risolvendo si ottiene**: $\tilde x_1 = 4$, $\tilde x_2 = 2$,
    $\tilde f = 24$, $\lambda = 8$.
    **Verifica**: vincolo attivo ($4 + 2 = 6$) e derivate parziali coincidenti:

    $$
    2\tilde x_1 = 8 = 4\tilde x_2 = \lambda . \quad ✓
    $$

    **Per perturbazione**: con termine noto 7, $\tilde f = 32{,}67 \approx 24 + 8$
    (più il termine di curvatura).

## Le condizioni di ottimalità non lineari: le KKT

Per $\min f(x_1, \dots, x_n)$ soggetto a $g_i(x_1, \dots, x_n) \le 0$ e
$h_j(x_1, \dots, x_n) = 0$, la Lagrangiana è

$$
L(x_1, \dots, x_n) = f(x_1, \dots, x_n)
+ \sum_{i=1}^{m} \lambda_i g_i(x_1, \dots, x_n)
+ \sum_{j=1}^{q} \nu_j h_j(x_1, \dots, x_n),
\qquad \lambda_i \ge 0 ;
$$

in un ottimo regolare $(\tilde x_1, \dots, \tilde x_n)$ esistono
$\lambda_i \ge 0$, $\nu_j$ con:

$$
\frac{\partial L}{\partial x_k}(\tilde x_1, \dots, \tilde x_n) = 0 \;\;
\forall k \in \{1, 2, \dots, n\},
\qquad \lambda_i\, g_i(\tilde x_1, \dots, \tilde x_n) = 0 \;\;
\forall i \in \{1, 2, \dots, m\} .
$$

Se il problema è convesso le KKT sono anche sufficienti. **Nel caso lineare le
KKT sono esattamente gli scarti complementari** della coppia (P)–(D): la
stazionarietà è l'ammissibilità del duale (moltiplicatori = $\pi_i$, e i
moltiplicatori dei vincoli di segno sono i costi ridotti), la complementarietà è
$\bar\pi_i \cdot \bar s_i = 0$. I moltiplicatori generalizzano i prezzi ombra;
quando i duali non sono disponibili, si stimano **per perturbazione** (aumentare
il termine noto di $\varepsilon$, ri-ottimizzare, rapporto incrementale).

!!! example "Le KKT sul QP dell'esempio"
    Sul modello $\min x_1^2 + 2x_2^2$ soggetto a $x_1 + x_2 \ge 6$:
    stazionarietà $2x_1 = \lambda$, $4x_2 = \lambda$; il vincolo dev'essere attivo
    (altrimenti $x_1 = x_2 = 0$ lo viola): $\lambda = 8$, $\tilde x_1 = 4$,
    $\tilde x_2 = 2$, $\tilde f = 24$ — gli stessi numeri di prima, ora dalla
    procedura generale. Con termine noto $6 + \varepsilon$ l'ottimo cresce di
    $\approx 8\varepsilon$ (esatto: $\tilde f(d) = \tfrac{2}{3}d^2$, quindi
    $24 + 8\varepsilon + \tfrac{2}{3}\varepsilon^2$).

## In sintesi

!!! chiave "In sintesi"

    - In un problema convesso ogni minimo locale è globale; un QP è convesso se e solo se $\boldsymbol Q \succeq 0$.

    - Le condizioni KKT sono stazionarietà della lagrangiana, ammissibilità e complementarità; nei problemi convessi sono sufficienti.

    - Nel caso lineare le condizioni KKT si riducono agli scarti complementari.

    - I moltiplicatori sono prezzi ombra, e si possono stimare anche per perturbazione.
