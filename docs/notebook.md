# I notebook del corso

Ogni capitolo con un modello ha il suo **notebook**: si apre in Google Colab con
un clic sul badge, installa il solver da sé e gira nel browser — sul computer non
serve installare niente. È lo stesso codice degli script di `python/`, cella per
cella, con le figure che compaiono sotto le celle invece di finire in un file.

!!! tip "La licenza del pacchetto pip basta"
    La licenza inclusa in `gurobipy` è limitata a 2000 variabili e 2000 vincoli, e
    tutti i modelli del corso ci stanno largamente: il più grande — la ricarica dei
    veicoli elettrici — ne usa 144 e 30. Per modelli più grandi si attiva la licenza
    accademica gratuita da [portal.gurobi.com](https://portal.gurobi.com).

| Capitolo | Classe | Notebook |
|---|---|---|
| [Produzione con smoothing quadratico](produzione-quadratica.md) | QP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab04_produzione_quadratica.ipynb) |
| [Supply chain con congestione e sostenibilità](supplychain.md) | LP / NLP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab05_supplychain.ipynb) |
| [Portafoglio di Markowitz](markowitz.md) | QP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab06_markowitz.ipynb) |
| [Pricing e revenue management](pricing.md) | NLP concavo / non convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab07_pricing.ipynb) |
| [Allocazione del budget pubblicitario](budget.md) | NLP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab08_budget.ipynb) |
| [Localizzazione continua di un servizio](localizzazione.md) | NLP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab09_localizzazione.ipynb) |
| [Ricarica di veicoli elettrici con profilo regolare](ricarica-ev-quadratica.md) | QP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab10_ricarica_ev_quadratica.ipynb) |
| [Capacità di servizio e tempi di attesa](code.md) | NLP convesso (coda M/M/1) | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab11_code.ipynb) |
| [Support Vector Machine: ottimizzazione per il machine learning](svm.md) | QP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab12_svm.ipynb) |
| [Regressione ai minimi quadrati](minimi-quadrati.md) | QP convesso | [![Apri in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fabiofurini/modellazione-pnl/blob/main/notebooks/lab13_minimi_quadrati.ipynb) |

## Come sono fatti

I notebook non si scrivono a mano: si generano dagli script con

```bash
python3 python/genera_notebook.py
```

Lo script del capitolo resta l'unica sorgente del codice — il notebook ne riprende
docstring, sezioni e commenti — e chi preferisce la riga di comando continua a
lanciare, dalla cartella `python/`:

```bash
python3 lab06_markowitz.py
```

## Installazione e licenza

Per lavorare in locale serve soltanto `gurobipy`:

```bash
python3 -m pip install gurobipy
```

Il pacchetto pip include una **licenza dimostrativa** (fino a 2000 variabili e 2000 vincoli):
sufficiente per tutti i modelli di questo laboratorio. All'avvio compare la riga
`Restricted license - for non-production use only`: è normale.

**Licenza accademica completa (gratuita):**

1. registrarsi su <https://portal.gurobi.com> con l'email istituzionale (`@uniroma1.it`);
2. richiedere una *Named-User Academic License*;
3. eseguire il comando `grbgetkey XXXXXXXX-...` mostrato dal portale (serve la rete di ateneo o VPN);
4. la licenza viene salvata in `~/gurobi.lic` e da quel momento non ci sono limiti di dimensione.

Verifica rapida:

```python
import gurobipy as gp
print(gp.gurobi.version())        # es. (13, 0, 3)
```

## Rigenerare tutto

```bash
python3 -m pip install gurobipy matplotlib pandas scipy   # scipy: solo funzioni statistiche
python3 python/esegui_tutti.py        # rigenera dati, risultati e figure
```

Nel [repository](https://github.com/fabiofurini/modellazione-pnl)
ci sono tutti gli **script Python** e i **dati** dei casi di studio in formato CSV.
