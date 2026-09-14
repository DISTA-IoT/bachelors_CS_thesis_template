# Template di Tesi di Laurea Triennale in Informatica
### Università degli Studi dell'Insubria — Dipartimento di Scienze Teoriche ed Applicate (DiSTA)

Modello ufficiale e guida metodologica per la redazione della tesi di laurea in **Informatica** (Corso di Studio in Informatica), allineato alle preferenze di ricerca e didattiche del **Prof. Jesús Cevallos** (docente di *Probabilità e Statistica per l'Informatica*).

---

## 🚀 Come Iniziare (Workflow Consigliato)

### 1. Fai il Fork della Repository
Consigliamo vivamente a ciascuno studente di **non scaricare un semplice file ZIP**, ma di effettuare un **Fork** di questa repository sul proprio account personale GitHub:
1. Clicca sul pulsante **Fork** in alto a destra su GitHub.
2. Assegna alla nuova repository il nome desiderato (es. `tesi-triennale-informatica`).
3. Avrai così a disposizione un repository Git personale che terrà traccia di tutta la storia delle modifiche, garantendo **backup automatico, versioning e sicurezza** contro ogni perdita di dati.

---

### 2. Scegli il Tuo Workspace di Scrittura

Puoi lavorare sulla tesi sia online sia in locale sul tuo computer.

#### Opzione A: Overleaf (Scrittura Cloud & Sincronizzazione Automatica con GitHub)
Overleaf permette di collegare direttamente un repository GitHub a un progetto:
1. Effettua l'accesso a [Overleaf](https://www.overleaf.com).
2. Se non l'hai già fatto, collega il tuo account GitHub nelle impostazioni del profilo:  
   *Account Settings* $\rightarrow$ *Integrations* $\rightarrow$ *Link GitHub Account*.
3. Dalla dashboard di Overleaf, clicca su:  
   **New Project** $\rightarrow$ **Import from GitHub**.
4. Seleziona il repository del tuo fork appena creato.
5. **Configurazione Compilatore su Overleaf**:
   - Apri il menu in alto a sinistra su Overleaf (*Menu*).
   - Verifica che il compilatore sia impostato su **pdfLaTeX** (o **LuaLaTeX**).
   - Verifica che *TeX Live version* sia impostata sull'anno più recente (2023 o 2024).
   - Verifica che il file principale (*Main document*) sia impostato su `main.tex`.
6. Da questo momento, qualsiasi commit effettuato su GitHub può essere sincronizzato su Overleaf e viceversa con un semplice comando di sincronizzazione (*Menu* $\rightarrow$ *GitHub* $\rightarrow$ *Sync / Push & Pull*).

#### Opzione B: Ambiente Locale (VS Code / TeXstudio / Neovim / CLI)
Se preferisci lavorare in locale sul tuo computer:
1. Clona il tuo fork:
   ```bash
   git clone git@github.com:<tuo-username>/<nome-repo>.git
   cd <nome-repo>
   ```
2. **Editor consigliato**: Visual Studio Code con l'estensione **LaTeX Workshop**, oppure TeXstudio.
3. **Compilazione**:
   Il progetto include la configurazione per `latexmk` e `biber`:
   ```bash
   latexmk -pdf main.tex
   ```
   Oppure la sequenza classica:
   ```bash
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```

---

## 🧭 Metodologia di Ricerca e Ordine di Scrittura

> [!IMPORTANT]
> **Scrivere l'Introduzione per ultima!**  
> L'errore più comune degli studenti è iniziare la tesi scrivendo l'Introduzione (Capitolo 1). Dedicare settimane all'introduzione prima di avere completato il codice e l'analisi sperimentale brucia energie preziose e porta a fallire lo **scope** del progetto.

L'ordine di stesura raccomandato è:
1. **Capitoli 4 e 5 (Implementazione e Risultati Sperimentali):** Si redigono subito dopo aver condotto la sperimentazione pratica e raccolto le metriche.
2. **Capitolo 3 (Progettazione del Sistema):** Formalizza l'architettura, i modelli matematici e le scelte ad alto livello.
3. **Capitolo 2 (Stato dell'Arte e Background):** Rivede la letteratura con la piena consapevolezza di cosa è servito davvero per realizzare il lavoro.
4. **Capitolo 6 (Conclusioni e Sviluppi Futuri):** Sintetizza gli obiettivi raggiunti e i limiti.
5. **Capitolo 1 (Introduzione) e Abstract:** **SOLO ALLA FINE**. Solo quando il lavoro è concluso si possiede la visione panoramica necessaria per introdurre la tesi in modo coerente e incisivo.

### Cos'è una "Tesi"?
Una tesi è una **risposta specifica (affermazione o negazione)** a una **domanda di ricerca (ipotesi)**:
- *Esempio di tesi:* "È possibile creare una procedura di migrazione automatica da framework X a linguaggio Y senza degradare le prestazioni di latenza per oltre il 15\% nelle condizioni A, B e C."
- Più l'affermazione è specifica e misurabile, più è solida e difendibile.
- La **domanda di ricerca** costituisce almeno il **60% del valore dell'intera tesi (6 punti su 10)**.

### Il Ruolo del Codice
Il codice sorgente in una tesi di laurea non è fine a se stesso né è un prodotto di ingegneria commerciale: è uno **strumento epistemico**, cioè lo strumento rigoroso che consente di rispondere alla domanda di ricerca con **zero ambiguità**.

---

## 📋 Regole Istituzionali e di Formattazione (Insubria DiSTA)

1. **Denominazioni Ufficiali**:
   - Ateneo: `UNIVERSITÀ DEGLI STUDI DELL'INSUBRIA`
   - Dipartimento: `DIPARTIMENTO DI SCIENZE TEORICHE ED APPLICATE`
   - Corso: `CORSO DI STUDIO IN INFORMATICA` *(non "Corso di Laurea")*
2. **Frontespizio**:
   - Lo studente inserisce direttamente **Nome e Cognome (+ Matricola)**, omettendo la dicitura "Candidato/a:" o "Tesi di Laurea di:".
3. **Codice Sorgente nella Tesi**:
   - **È vietato inserire blocchi di codice giganteschi**. Il listato sorgente va limitato a brevi snippet mirati (10–20 righe) per logiche algoritmiche critiche.
   - Per tutto il resto si devono usare: **pseudocodice formale** (ambiente `algorithm` + `algpseudocode`), **diagrammi architetturali** e **diagrammi di flusso (flowchart)**.
4. **Tabelle e Figure**:
   - Usare sempre tabelle scientifiche con il pacchetto `booktabs` (**nessuna linea verticale**).
   - Figure vettoriali (PDF) o raster ad alta definizione (PNG a 300 DPI), sempre con `\caption` e `\label`, e **sempre citate esplicitamente nel testo** con `\Cref{...}`.
5. **Bibliografia Accademica**:
   - **Minimo 20 citazioni scientifiche autorevoli** nel file `biblio.bib` (`@article`, `@inproceedings`, `@book`, `@techreport`), gestite tramite `biblatex` e `biber`. Evitare sitografie generiche o link web non accademici.

---

## 📁 Struttura della Repository

```text
.
├── main.tex                  # File master (preambolo, frontespizio, indici, inclusione capitoli)
├── biblio.bib                # Archivio bibliografico BibLaTeX (20+ fonti accademiche curate)
├── Cap1_introduzione.tex      # Guida metodologica, tesi, ipotesi, scope e pipeline
├── Cap2_background.tex        # Stato dell'arte, revisione della letteratura e guida citazioni
├── Cap3_sistema.tex           # Architettura, diagrammi, tabelle booktabs ed equazioni
├── Cap4_implementazione.tex   # Tecnologie, buone pratiche e regole per i listati di codice
├── Cap5_risultati.tex         # Metodologia di test, tabelle comparative e analisi critica
├── Cap6_conclusioni.tex       # Valutazione obiettivi, limiti e sviluppi futuri
├── img/                       # Cartella figure (logo Insubria, diagrammi di esempio)
│   ├── logo_insu.jpeg
│   ├── placeholder_figura.png # Diagramma architetturale (Wikimedia Commons)
│   └── placeholder_flusso.png # Flowchart decisionale standard (Wikimedia Commons)
└── .gitignore                 # Regole per escludere file ausiliari di compilazione LaTeX
```

---

## ⚖️ Note per Altri Relatori
Questo template e le linee guida incorporate riflettono la visione metodologica del **Prof. Jesús Cevallos** per le tesi del Corso di Studio in Informatica dell'Università degli Studi dell'Insubria. Gli studenti che svolgono la tesi con altri docenti relatori dovrebbero verificare eventuali preferenze o specifiche editoriali del proprio relatore.
