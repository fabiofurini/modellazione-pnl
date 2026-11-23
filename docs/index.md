---
hide:
  - navigation
  - toc
---

<div class="cantiere" markdown style="text-align:center">

![Lavori in corso: sito e materiale didattico sono ancora in costruzione](img/cantiere.svg){ width="560" }

**Sito in costruzione.** Alcune parti, come i richiami sulle condizioni KKT, saranno completate insieme al
corso di [Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/).

</div>

<div class="hero" markdown>

# Modellazione PNL

<!-- collana-riga -->
<p class="collana-riga" markdown>Un corso della collana <b>Ricerca Operativa e Matematica</b> · [tutti i corsi](#la-collana)</p>
<!-- /collana-riga -->

Materiale didattico ideato e sviluppato da **[Fabio Furini](https://fabiofurini.github.io/)**, professore
associato al [DIAG](https://www.diag.uniroma1.it/), Sapienza Università di Roma.

Il corso presenta la modellazione con la programmazione non lineare: richiami di teoria, i solver per i
modelli non lineari, e i modelli di produzione con smoothing quadratico, supply chain e CO2, portafoglio
di Markowitz, pricing, budget pubblicitario, localizzazione continua, code, support vector machine e
minimi quadrati, con il codice Python/Gurobi.

Prerequisiti: [Modellazione PL](https://fabiofurini.github.io/modellazione-pl/) e [Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/).

[Comincia :material-arrow-right:](strumenti.md){ .md-button .md-button--primary }
[:material-pencil: Esercizi](esercizi/index.md){ .md-button }
[:material-gesture-tap: Laboratorio](laboratorio/index.md){ .md-button }
[:material-clipboard-check-outline: Quiz](autovalutazione.md){ .md-button }
[:material-download: Materiale](materiale.md){ .md-button }

</div>

<!-- collana-app -->
## Provalo subito

Tre modelli non lineari del corso risolti all'ottimo nel browser: portafoglio di Markowitz, prezzo ottimo con capienza e localizzazione di un servizio. Scegli il modello in alto a destra, cambia il rendimento richiesto o gli altri dati con i cursori e guarda la soluzione ottima ricalcolata, con la sua posizione sulla frontiera efficiente.

<div class="gi" data-grafico="pnl-modelli"></div>

[:material-gesture-tap: Altre app nel laboratorio](laboratorio/index.md){ .md-button }
<!-- /collana-app -->

## Le parti del corso

<div class="grid cards" markdown>

-   :material-hammer-wrench: **Strumenti**

    ---

    Convessità, programmazione quadratica e condizioni KKT; i comandi del solver
    per i modelli non lineari e i moltiplicatori dei QP.

    [:octicons-arrow-right-24: I capitoli](strumenti.md)

-   :material-factory: **Modelli deterministici**

    ---

    Produzione con smoothing, supply chain, portafoglio, prezzi, budget,
    localizzazione, ricarica dei veicoli elettrici, code: tutti i dati sono noti.

    [:octicons-arrow-right-24: Gli otto problemi](modelli-deterministici.md)

-   :material-robot: **Ottimizzazione e machine learning**

    ---

    La SVM e i minimi quadrati come QP convessi: margine, duale, support vector,
    equazioni normali — senza librerie di ML.

    [:octicons-arrow-right-24: I due problemi](ottimizzazione-ml.md)

</div>

<!-- collana-da-non-perdere -->
## Da non perdere

<div class="grid cards" markdown>

-   :material-pencil-box-multiple: **Esercizi**

    ---

    Esercizi di modellazione per ogni capitolo, di livello d'esame, sui casi del corso.

    [:octicons-arrow-right-24: Gli esercizi](esercizi/index.md)

-   :material-clipboard-check-outline: **Quiz di autovalutazione**

    ---

    Un facsimile d'esame nuovo a ogni avvio: 13 domande, 33 punti, con la soluzione e il link alle dispense. In Materiale c'è anche la banca completa delle domande.

    [:octicons-arrow-right-24: Mettiti alla prova](autovalutazione.md)

-   :material-gesture-tap: **Laboratorio interattivo**

    ---

    App che girano nel browser: muovi i parametri e guarda le idee del corso lavorare, un passo alla volta.

    [:octicons-arrow-right-24: Il laboratorio](laboratorio/index.md)

-   :material-download: **Dispense in PDF**

    ---

    Dispense, eserciziari e slide in PDF, con la stessa numerazione del sito.

    [:octicons-arrow-right-24: Il materiale](materiale.md)

-   :material-language-python: **Notebook in Colab**

    ---

    Il codice del corso che gira nel browser, senza installare niente.

    [:octicons-arrow-right-24: I notebook](notebook.md)

-   :material-format-list-numbered: **Indice completo**

    ---

    Tutti i capitoli con le loro sezioni in una pagina, e come è fatto ogni capitolo.

    [:octicons-arrow-right-24: L'indice](programma.md)

</div>
<!-- /collana-da-non-perdere -->

---

<!-- collana -->
## La collana

Tutti i corsi della collana hanno la stessa impostazione: dispense online e in PDF, esercizi con le soluzioni, laboratorio interattivo e quiz di autovalutazione.

<div class="grid cards" markdown>

-   :material-function-variant: **[Analisi Matematica 1](https://fabiofurini.github.io/analisi-matematica-1/)**

    numeri reali, funzioni, limiti, derivate e serie, con i grafici interattivi

-   :material-matrix: **[Algebra lineare](https://fabiofurini.github.io/algebra-lineare/)**

    vettori, matrici, determinanti, sistemi lineari e autovalori, con il laboratorio di calcolo

-   :material-code-braces: **[Algoritmi](https://fabiofurini.github.io/algoritmi/)**

    rappresentazione dei numeri, pseudocodice, ordinamento e ricerca, analisi e algoritmi ricorsivi

-   :material-vector-triangle: **[Programmazione lineare](https://fabiofurini.github.io/programmazione-lineare/)**

    poliedri, algoritmo del simplesso, dualità e simplesso duale, con il laboratorio interattivo

-   :material-dots-grid: **[Programmazione lineare intera](https://fabiofurini.github.io/programmazione-lineare-intera/)**

    rilassamento continuo, disuguaglianze valide, piani di taglio, branch-and-bound e branch-and-cut

-   :material-vector-curve: **[Ottimizzazione convessa](https://fabiofurini.github.io/ottimizzazione-convessa/)**

    insiemi e funzioni convesse, problemi di ottimizzazione convessa, con grafici interattivi

-   :material-graph-outline: **[Ottimizzazione su reti](https://fabiofurini.github.io/ottimizzazione-su-reti/)**

    grafi, alberi ricoprenti, cammini minimi, flussi su reti, simplesso su reti e gestione dei progetti

-   :material-hexagon-multiple-outline: **[Problemi di ottimizzazione combinatoria](https://fabiofurini.github.io/ottimizzazione-combinatoria/)**

    zaino, bin packing, colorazione, TSP, scheduling e lot sizing: i problemi, le formulazioni e gli algoritmi ad hoc

-   :material-table-large: **[Programmazione dinamica](https://fabiofurini.github.io/programmazione-dinamica/)**

    principi e algoritmi di PD per zaino, lot sizing, cambio monete e taglio delle aste

-   :material-map-marker-path: **[Algoritmi euristici](https://fabiofurini.github.io/algoritmi-euristici/)**

    euristiche costruttive, ricerca locale, metaeuristiche ed euristiche MIP per i problemi di ottimizzazione combinatoria

-   :material-approximately-equal: **[Algoritmi di approssimazione](https://fabiofurini.github.io/algoritmi-di-approssimazione/)**

    garanzie di prestazione, schemi di approssimazione e limiti dell'approssimazione per i problemi combinatori

-   :material-chart-line: **[Modellazione PL](https://fabiofurini.github.io/modellazione-pl/)**

    modelli di programmazione lineare per problemi gestionali, risolti con Python e Gurobi

-   :material-chart-bell-curve-cumulative: **Modellazione PNL** · *questo corso*

    modelli di programmazione non lineare, dal portafoglio al machine learning, con Python e Gurobi

-   :material-vector-polygon: **[Modellazione MIP](https://fabiofurini.github.io/modellazione-mip/)**

    modelli di programmazione lineare a variabili intere, dalla formulazione alla soluzione con i solver

</div>
<!-- /collana -->

---

Materiale didattico di **[Fabio Furini](https://fabiofurini.github.io/)** —
[DIAG](https://www.diag.uniroma1.it/), Sapienza Università di Roma.
