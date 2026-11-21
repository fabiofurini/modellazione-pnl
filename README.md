<h3 align="center">Materiale didattico di
<a href="https://fabiofurini.github.io/">Fabio Furini</a></h3>
<p align="center">
  Professore associato di Ricerca Operativa ·
  <a href="https://www.diag.uniroma1.it/">DIAG</a>, Sapienza Università di Roma ·
  <a href="https://fabiofurini.github.io/">sito personale</a>
</p>

# Modellazione PNL

> **L'autore.** Fabio Furini è professore associato al DIAG della Sapienza dal
> settembre 2021. Dottorato in Automatica e Ricerca Operativa all'Università di
> Bologna (2011) e assegno di ricerca fino al 2012; postdoc all'Université
> Paris-13 (2012–2013); dal 2013 al 2019 *Maître de Conférences* all'Université
> Paris-Dauphine. *Habilitation à Diriger des Recherches* in Francia nel 2017 e
> Abilitazione Scientifica Nazionale a professore ordinario in Ricerca Operativa
> nel 2019. Nel 2020 ricercatore CNR presso l'IASI-CNR di Roma.
> Sito personale: <https://fabiofurini.github.io/>

Modelli di programmazione non lineare — la dispensa del corso in versione online, con
codice Python/Gurobi e casi di studio riproducibili. Prerequisiti:
[Modellazione PL](https://fabiofurini.github.io/modellazione-pl/) e
[Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/).

**📖 Dispensa online: [fabiofurini.github.io/modellazione-pnl](https://fabiofurini.github.io/modellazione-pnl/)**

**▶️ Notebook eseguibili in Colab: [l'elenco dei capitoli](https://fabiofurini.github.io/modellazione-pnl/notebook/)** — girano nel browser, senza installare niente.

## Scarica in PDF

- [Dispensa completa](https://fabiofurini.github.io/modellazione-pnl/pdf/dispensa-modellazione-pnl.pdf)
- [Slide delle lezioni](https://fabiofurini.github.io/modellazione-pnl/materiale/), una per capitolo, nella pagina del materiale

## Indice

**Strumenti**

- [Teoria: ottimizzazione non lineare](https://fabiofurini.github.io/modellazione-pnl/teoria-non-lineare/) — convessità, QP, condizioni KKT
- [Solver: modelli non lineari](https://fabiofurini.github.io/modellazione-pnl/solver-non-lineare/) — obiettivi quadratici, vincoli funzionali e bilineari, moltiplicatori

**Modelli deterministici**

- [Produzione con smoothing quadratico](https://fabiofurini.github.io/modellazione-pnl/produzione-quadratica/) — QP convesso
- [Supply chain con congestione e CO₂](https://fabiofurini.github.io/modellazione-pnl/supplychain/) — NLP convesso
- [Portafoglio di Markowitz](https://fabiofurini.github.io/modellazione-pnl/markowitz/) — QP convesso
- [Pricing e revenue management](https://fabiofurini.github.io/modellazione-pnl/pricing/) — NLP
- [Budget pubblicitario](https://fabiofurini.github.io/modellazione-pnl/budget/) — NLP convesso
- [Localizzazione continua](https://fabiofurini.github.io/modellazione-pnl/localizzazione/) — NLP convesso
- [Ricarica di veicoli elettrici con profilo regolare](https://fabiofurini.github.io/modellazione-pnl/ricarica-ev-quadratica/) — QP convesso
- [Code e capacità di servizio](https://fabiofurini.github.io/modellazione-pnl/code/) — NLP convesso

**Ottimizzazione e machine learning**

- [Support Vector Machine](https://fabiofurini.github.io/modellazione-pnl/svm/) — QP convesso
- [Regressione ai minimi quadrati](https://fabiofurini.github.io/modellazione-pnl/minimi-quadrati/) — QP convesso

**Il corso**

- [Organizzazione del corso](https://fabiofurini.github.io/modellazione-pnl/organizzazione/) — laboratori ed errori da evitare

## Eseguire i modelli

Ogni capitolo ha il suo script in [`python/`](python/) (`lab04`–`lab13`):

```bash
python3 -m pip install gurobipy matplotlib pandas
python3 python/esegui_tutti.py     # tutti i modelli: risultati, figure e notebook
```

Senza installare niente, ogni capitolo ha il suo notebook in [`notebooks/`](notebooks/): si apre in
Colab dal badge in cima alla pagina del capitolo e gira nel browser. I notebook si generano dagli
script (`python3 python/genera_notebook.py`), quindi il codice del corso resta uno solo. I dati dei
casi presi da Modellazione PL (produzione, ricarica EV, panetteria) stanno nel repository di
[Modellazione PL](https://github.com/fabiofurini/modellazione-pl): gli script qui li riscrivono con
gli stessi valori.

## Licenza

- **Testi, figure e dati** (`docs/`, `dati/`): [CC BY 4.0](LICENSE) — chiunque può
  riusarli, adattarli e ridistribuirli, anche in altri corsi, citando l'autore.
- **Codice Python** (`python/`): [MIT](LICENSE-CODE), la licenza usuale per il
  software, così il riuso degli script non ha ambiguità.

Per citare il materiale c'è [`CITATION.cff`](CITATION.cff): GitHub ne ricava la
voce *Cite this repository*. Le soluzioni degli esercizi non sono pubblicate:
vengono distribuite a lezione.

## English version

The whole course is also available in English:
**[fabiofurini.github.io/nlp-modelling](https://fabiofurini.github.io/nlp-modelling/)**
([repository](https://github.com/fabiofurini/nlp-modelling)).

## Della stessa collana

- [Modellazione PL](https://fabiofurini.github.io/modellazione-pl/)
- [Modellazione MIP](https://fabiofurini.github.io/modellazione-mip/)
- [Analisi Matematica 1](https://fabiofurini.github.io/analisi-matematica-1/)
- [Algebra lineare](https://fabiofurini.github.io/algebra-lineare/)
- [Programmazione lineare](https://fabiofurini.github.io/programmazione-lineare/)
- [Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/)
- [Algoritmi](https://fabiofurini.github.io/algoritmi/)

---

Materiale didattico di **[Fabio Furini](https://fabiofurini.github.io/)** — [DIAG](https://www.diag.uniroma1.it/), Sapienza Università di Roma.
Le soluzioni degli esercizi vengono distribuite a lezione.
