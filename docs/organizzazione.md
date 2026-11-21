# Organizzazione del corso

<!-- collana-dalla-home -->
## Il corso in breve

**10 capitoli applicativi · 3 capitoli di strumenti · QP e NLP · un notebook Colab per
capitolo · codice Python/Gurobi riproducibile.** L'elenco completo sta nel
[programma](programma.md). Il corso segue
[Modellazione PL](https://fabiofurini.github.io/modellazione-pl/), da cui riprende
notazione, comandi generali del solver e protocollo di sensitività.

## Scarica in PDF

- 📘 **[Dispensa completa](pdf/dispensa-modellazione-pnl.pdf)** — modelli, esempi svolti, casi di studio, analisi di sensitività
- 📊 **[Slide delle lezioni](materiale.md)** — una per capitolo, nella pagina del [materiale](materiale.md)

## Per cominciare

Non serve installare niente: ogni capitolo ha il suo
[notebook che si apre in Colab](notebook.md) e gira nel browser.
<!-- /collana-dalla-home -->

## Percorso essenziale in quattro laboratori

| | Contenuto | Obiettivi di apprendimento |
|---|---|---|
| **Lab 1** | Markowitz | costruire un QP convesso; tracciare una frontiera; discutere la fragilità delle stime |
| **Lab 2** | Produzione con smoothing | aggiungere un termine quadratico a un modello lineare; leggere e verificare i moltiplicatori di un QP |
| **Lab 3** | Pricing *oppure* budget | modellare funzioni non lineari; studiare la concavità; verificare le KKT numericamente |
| **Lab 4** | Progetto a scelta | supply chain, localizzazione, ricarica EV, code, SVM o minimi quadrati; presentazione manageriale |

## Gli errori più comuni

1. Leggere `.X` o `.Pi` senza controllare `m.Status`.
2. Dimenticare `lb=-GRB.INFINITY` sulle variabili libere ($b$ della SVM, i residui dei minimi quadrati).
3. Usare il moltiplicatore di un QP per un incremento grande: è esatto solo al margine.
4. Dimenticare `NonConvex = 2` con termini bilineari, o credere convesso un problema che non lo è.
5. Aggiornare il RHS di un vincolo con costanti a sinistra.
6. Ottimizzare un solo obiettivo quando ce ne sono due.
7. Scegliere gli iperparametri guardando il test set.
8. Riportare sei cifre decimali da stime che ballano alla seconda.

## Riproducibilità

```bash
python3 -m pip install gurobipy matplotlib pandas
python3 python/esegui_tutti.py       # rigenera risultati, figure e notebook
```

Le soluzioni degli esercizi vengono distribuite a lezione.
