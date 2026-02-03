# Guida: Aggiungere una Nuova Edizione del Master

Questa guida descrive dettagliatamente tutti i file che devono essere creati e modificati per aggiungere una nuova edizione del Master Big Data.

## Aggiornamenti Recenti (Febbraio 2026)

### Pulizia Repository
Il repository è stato ripulito rimuovendo contenuti obsoleti e non utilizzati:
- **Pagine eliminate**: `bootstrap.markdown`, `installation.markdown`, `jekyll-ssg.markdown`, `kramdown.markdown`, `markdown.markdown`, `obiettivi.markdown`, `single.markdown`
- **Componenti HTML eliminate**: Diversi componenti custom non più utilizzati (`big-numbers.html`, `code-explanation.html`, `img-selector.html`, `modal-component-intro.html`, `modal-component-mappa.html`, etc.)
- **Snippet eliminati**: Frammenti non essenziali di documentazione e sezioni dedicate a contenuti storici

### Miglioramenti Recenti
- **Evento Inaugurazione**: Aggiunta della sezione "Evento Inaugurazione" alla home page del master con schedule dettagliato
- **Sezione Status**: Implementazione della funzione `getStatoScadenza()` per visualizzare dinamicamente lo stato delle scadenze di iscrizione
- **Styling Ottimizzato**: Miglioramenti di responsive design per la sezione contatti, evento e footer
- **Deadlines Dinamiche**: Aggiunta del sistema dinamico per la gestione delle scadenze di iscrizione (campo `scadenze` in `_data/master_info.json`)
- **Navbar Responsiva**: Migliorato il design della navbar per una migliore visualizzazione su dispositivi mobile
- **Pagine Consiglio Direttivo**: Aggiunte pagine dedicate al consiglio direttivo per ogni edizione del master (layout `direttivo`)

## Indice
1. [File di Configurazione Edizioni](#1-file-di-configurazione-edizioni)
2. [File dei Dati Didattici](#2-file-dei-dati-didattici)
3. [Pagina Didattica](#3-pagina-didattica)
4. [File dei Dati Studenti](#4-file-dei-dati-studenti)
5. [Pagina Studenti](#5-pagina-studenti)
6. [File dei Dati Docenti](#6-file-dei-dati-docenti)
7. [Pagine Docenti e Direttivo](#7-pagine-docenti-e-direttivo)
8. [Aggiornamento delle Scadenze Importanti](#9-aggiornamento-delle-scadenze-importanti)
9. [Aggiornamento Informazioni Generali](#8-aggiornamento-informazioni-generali)
10. [Checklist Finale](#10-checklist-finale)

---

## 1. File di Configurazione Edizioni

### File: `_data/edizioni.yml`

**Percorso**: `_data/edizioni.yml`

**Cosa fare**: Aggiungere la nuova edizione 2026-2027 in **testa al file** (prima posizione) e impostare il flag `active: true` per questa edizione, mentre si deve cambiare `active: false` per l'edizione precedente.

**Struttura da aggiungere**:
```yaml
- label: "2026-2027"
  year: "26-27"
  year_label: "2026-2027"
  url: "/didattica/26-27"
  data_file: didattica_26_27
  active: true
```

**Note importanti**:
- `label`: Etichetta visibile nell'interfaccia utente (formato "YYYY-YYYY")
- `year`: Formato abbreviato usato internamente (formato "YY-YY")
- `year_label`: Etichetta estesa dell'anno (formato "YYYY-YYYY")
- `url`: URL della pagina didattica per questa edizione
- `data_file`: Nome del file YAML (senza estensione) che conterrà i dati dei corsi
- `active`: Deve essere `true` solo per l'edizione corrente

**Esempio di modifica**:
```yaml
# _data/edizioni.yml
# Lista di tutte le edizioni della didattica

- label: "2026-2027"
  year: "26-27"
  year_label: "2026-2027"
  url: "/didattica/26-27"
  data_file: didattica_26_27
  active: true

- label: "2025-2026"
  year: "25-26"
  year_label: "2025-2026"
  url: "/didattica/25-26"
  data_file: didattica_25_26
  active: false  # <-- CAMBIARE DA true A false

# ... resto delle edizioni precedenti
```

---

## 2. File dei Dati Didattici

### File: `_data/didattica/didattica_26_27.yml`

**Percorso**: `_data/didattica/didattica_26_27.yml`

**Cosa fare**: Creare un nuovo file YAML contenente tutti i corsi dell'edizione 2026-2027.

**Consiglio**: Copiare il file dell'edizione precedente (`didattica_25_26.yml`) come base e modificarlo.

**Struttura di ogni corso**:
```yaml
- title: "Nome del Corso"
  credits: 5              # Crediti formativi universitari (CFU)
  hours: 60               # Ore totali del corso
  area: "Area Tematica"   # Area di appartenenza del corso
  description: "Descrizione dettagliata del corso e degli argomenti trattati."
```

**Aree tematiche comuni**:
- Big Data Technology
- Big Data Mining
- Big Data Ethics
- Big Data for Social Good
- Big Data Sensing & Procurement
- Visual Analytics
- Machine Learning
- Statistics & Data Analysis

**Esempio completo**:
```yaml
# Struttura dei corsi per l'anno accademico 2026-2027

- title: "Alignment"
  credits: 5
  hours: 60
  area: "Big Data Technology"
  description: "Allineamento delle competenze in informatica e analisi di base."

- title: "Data Mining & Machine Learning"
  credits: 6
  hours: 72
  area: "Big Data Mining"
  description: "Modulo centrale sul processo di knowledge discovery e apprendimento automatico."

- title: "Big Data Ethics"
  credits: 2
  hours: 24
  area: "Big Data Ethics"
  description: "Nozioni etiche e legali di privacy, anonimato e discriminazione."

# ... aggiungi tutti gli altri corsi
```

**Note importanti**:
- Ogni corso deve avere tutti i campi compilati
- I crediti sono tipicamente tra 2 e 6 CFU
- Le ore sono calcolate come: crediti × 12 (circa)
- Mantenere una descrizione chiara e concisa per ogni corso

---

## 3. Pagina Didattica

### File: `_pages/didattica/didattica_26_27.markdown`

**Percorso**: `_pages/didattica/didattica_26_27.markdown`

**Cosa fare**: Creare una nuova pagina Markdown per la didattica dell'edizione 2026-2027.

**Consiglio**: Copiare il file `didattica_25_26.markdown` come base.

**Struttura del file**:
```markdown
---
layout: didattica
title: "Didattica 2026-2027"
permalink: /didattica/26-27
data_source: didattica_26_27
header_type: sbd
header_img: assets/images/header.svg
header_title: " "
---

Il **Master Big Data** è un master full-time erogato interamente online che avrà durata di un anno a partire da Novembre. L'attività didattica prevede due fasi principali:

- **Prima fase** (Novembre - Luglio): dedicata alle lezioni frontali e attività progettuali
- **Seconda fase** (Agosto - Dicembre): dedicata al tirocinio di 425 ore presso i nostri partner

## Organizzazione Didattica

L'attività didattica settimanale durante la prima fase prevede alcune ore di lezioni frontali concentrate dal **mercoledì al sabato** e delle ore di laboratorio durante le quali gli studenti potranno esercitarsi sperimentando sul campo i metodi presentati a lezione con il supporto di tutor.

Il Consiglio del Master ha stabilito che, per il conseguimento del titolo, è richiesta la **presenza dello studente ad almeno il 70%** delle ore complessive di lezioni frontali e di laboratorio.

### Crediti Formativi Universitari (CFU)

Il Credito Formativo Universitario (CFU) è l'unità di misura del volume di lavoro di apprendimento, richiesto ad un allievo in possesso di adeguata preparazione iniziale, per l'acquisizione di conoscenze ed abilità richieste da una certa attività formativa. 

Esso corrisponde a **25 ore di lavoro complessivo**, che comprende sia le ore di didattica frontale, sia lo studio individuale, sia altri tipi di attività (come il tirocinio). Ogni attività formativa ha associato un certo numero di crediti, che vengono acquisiti con il superamento di una verifica del profitto.

L'attività didattica sarà supportata dall'uso della **piattaforma Moodle**, dove gli studenti troveranno tutto il materiale didattico.
```

**Elementi del front matter** (parte tra `---`):
- `layout: didattica` - Layout specifico per le pagine di didattica
- `title` - Titolo della pagina (aggiornare l'anno)
- `permalink` - URL della pagina (deve corrispondere a quello in `edizioni.yml`)
- `data_source` - Nome del file dati YAML (senza estensione, deve corrispondere a `data_file` in `edizioni.yml`)
- `header_type`, `header_img`, `header_title` - Configurazione dell'header della pagina

**Contenuto**:
- Puoi personalizzare il contenuto markdown se ci sono cambiamenti specifici per l'edizione 2026-2027
- In genere, il contenuto è standard tra le edizioni

---

## 4. File dei Dati Studenti

### File: `_data/studenti/studenti_26_27.yml`

**Percorso**: `_data/studenti/studenti_26_27.yml`

**Cosa fare**: Creare un nuovo file YAML per gli studenti dell'edizione 2026-2027.

**Nota**: All'inizio dell'anno accademico, questo file conterrà solo un placeholder. Verrà aggiornato man mano che gli studenti si iscrivono.

**Struttura iniziale (placeholder)**:
```yaml
# _data/studenti/studenti_26_27.yml
# Elenco studenti Master Big Data 2026-2027

# Placeholder per studenti dell'anno 2026-2027
- nome: "In attesa di dati"
  anno_accademico: "2026-2027"
  bio: "Studenti del Master 2026-2027 - Dati in aggiornamento"
  image: "/assets/images/studenti/placeholder.jpg"
```

**Struttura per studenti reali** (da aggiungere successivamente):
```yaml
- nome: "Mario Rossi"
  anno_accademico: "2026-2027"
  bio: "Laureato in Informatica presso l'Università di Pisa. Appassionato di machine learning e analisi dati."
  linkedin: "https://linkedin.com/in/mariorossi"  # opzionale
  github: "https://github.com/mariorossi"         # opzionale
  email: "mario.rossi@example.com"                # opzionale
  image: "/assets/images/studenti/26_27/mario_rossi.jpg"
  
- nome: "Laura Bianchi"
  anno_accademico: "2026-2027"
  bio: "Laureata in Statistica, interessata all'applicazione dei big data nel settore healthcare."
  linkedin: "https://linkedin.com/in/laurabianchi"
  image: "/assets/images/studenti/26_27/laura_bianchi.jpg"

# ... aggiungi tutti gli altri studenti
```

**Campi disponibili per ogni studente**:
- `nome` (obbligatorio): Nome completo dello studente
- `anno_accademico` (obbligatorio): Anno accademico di riferimento
- `bio` (obbligatorio): Breve biografia/descrizione dello studente
- `image` (obbligatorio): Percorso dell'immagine profilo
- `linkedin` (opzionale): Link al profilo LinkedIn
- `github` (opzionale): Link al profilo GitHub
- `email` (opzionale): Email di contatto

**Note sulle immagini**:
- Creare una cartella `assets/images/studenti/26_27/` per le foto degli studenti
- Formato consigliato: JPG o PNG
- Dimensioni consigliate: 400×400 px (quadrate)
- Usare nomi file lowercase e senza spazi (es: `mario_rossi.jpg`)

---

## 5. Pagina Studenti

### File: `_pages/studenti/studenti_26_27.markdown`

**Percorso**: `_pages/studenti/studenti_26_27.markdown`

**Cosa fare**: Creare una nuova pagina Markdown per visualizzare gli studenti dell'edizione 2026-2027.

**Contenuto del file**:
```markdown
---
layout: people
title: "Studenti"
permalink: /studenti/26-27/
header_type: sbd
header_img: assets/images/header.svg
header_title: " "
data_source: studenti_26_27
data_type: studenti
description: "Gli studenti del Master in Big Data Analytics provengono da percorsi formativi diversi e contribuiscono con le loro competenze uniche all'esperienza del master."
---
```

**Elementi del front matter**:
- `layout: people` - Layout specifico per visualizzare persone (studenti)
- `title` - Titolo della pagina
- `permalink` - URL della pagina (formato: `/studenti/YY-YY/`)
- `data_source` - Nome del file dati YAML degli studenti (senza estensione)
- `data_type: studenti` - Tipo di dati (distingue tra studenti, docenti, etc.)
- `description` - Descrizione meta per SEO

**Note**:
- Il contenuto markdown può essere lasciato vuoto (tutto è gestito dal layout)
- Il layout `people` si occuperà automaticamente di visualizzare i dati dal file YAML

---File dei Dati Docenti

**Percorso**: `_data/docenti/docenti_26_27.yml`

**Cosa fare**: Creare un nuovo file YAML contenente tutti i docenti dell'edizione 2026-2027, sia il **Consiglio Direttivo** che i **Docenti e Ricercatori**.

**Consiglio**: Copiare il file dell'edizione precedente (`docenti_25_26.yml`) come base e aggiornarlo con eventuali cambiamenti.

**Nota importante**: A differenza di studenti e didattica, il file docenti contiene sia i membri del consiglio direttivo che tutti gli altri docenti. Il file è unico e viene filtrato tramite il campo `role` nelle diverse pagine.

**Struttura del file**:

```yaml
# _data/docenti/docenti_26_27.yml
# Elenco completo docenti Master Big Data 2026-2027

# --- CONSIGLIO DIRETTIVO ---
- name: "Dino Pedreschi"
  role: "Direttore del Master"
  institution: "Università di Pisa"
  bio: "Pioniere del mobility data mining e social network mining. Coordina il KDD Lab."
  image: "/assets/images/docenti/pedreschi.png"
  linkedin: "https://www.linkedin.com/in/dinopedreschi/"  # opzionale
  website: "http://kdd.isti.cnr.it/people/pedreschi"      # opzionale

- name: "Anna Monreale"
  role: "Vice-Direttrice"
  institution: "Università di Pisa"
  bio: "Esperta di Explainable AI e Privacy-by-design. Ricercatrice del KDD Lab."
  image: "/assets/images/docenti/Monreale.jpeg"
  
- name: "Fosca Giannotti"
  role: "Consiglio Direttivo"
  institution: "Scuola Normale Superiore"
  bio: "Scenziata di fama internazionale nel campo del data mining e dell'IA etica."
  image: "/assets/images/docenti/fosca-giannotti.jpg"

# ... altri membri del consiglio direttivo

# --- DOCENTI E RICERCATORI ---
- name: "Riccardo Guidotti"
  role: "Docente"
  institution: "Università di Pisa"
  bio: "Esperto di interpretabilità dei modelli black-box e analisi di serie temporali."
  image: "/assets/images/docenti/riccardo-guidotti.jpg"
  email: "riccardo.guidotti@unipi.it"  # opzionale

- name: "Giulio Rossetti"
  role: "Docente"
  institution: "ISTI-CNR"
  bio: "Focalizzato su Complex Network Analysis e diffusione di informazioni."
  image: "/assets/images/docenti/giulio-rossetti.jpg"

# ... altri docenti
```

**Campi disponibili per ogni docente**:
- `name` (obbligatorio): Nome completo del docente
- `role` (obbligatorio): Ruolo del docente. Valori possibili:
  - `"Direttore del Master"` - Per il direttore
  - `"Vice-Direttrice"` / `"Vice-Direttore"` - Per il vice direttore
  - `"Consiglio Direttivo"` - Per i membri del consiglio direttivo
  -9`"Docente"` - Per tutti gli altri docenti e ricercatori
- `institution` (obbligatorio): Istituzione di appartenenza
- `bio` (obbligatorio): Breve biografia con competenze ed expertise
- `image` (obbligatorio): Percorso dell'immagine profilo
- `linkedin` (opzionale): Link al profilo LinkedIn
- `website` (opzionale): Sito web personale o pagina istituzionale
- `email` (opzionale): Email di contatto

**Organizzazione del file**:
1. **Prima sezione**: Consiglio Direttivo (role: "Direttore del Master", "Vice-Direttrice", "Consiglio Direttivo")
   - Iniziare con Direttore e Vice-Direttore
   - Poi elencare gli altri membri del consiglio
2. **Seconda sezione**: Docenti e Ricercatori (role: "Docente")
   - Elencare tutti gli altri docenti del master

**Aggiornamenti tipici tra edizioni**:
- Nuovi docenti che si aggiungono al corpo docente
- Docenti che non sono più attivi nell'edizione corrente
- Cambiamenti di ruolo (es. nuovo vice-direttore)
- Aggiornamento delle bio con nuove competenze o progetti
- Aggiornamento istituzioni di appartenenza

**Note sulle immagini**:
- Le foto dei docenti sono generalmente condivise tra le edizioni
- Percorso standard: `assets/images/docenti/nome-cognome.jpg`
- Se aggiungi nuovi docenti, crea le relative immagini
- Formato consigliato: JPG o PNG
- Dimensioni consigliate: 400×400 px (quadrate)

---

## 7. Pagine Docenti e Direttivo

### File: `_pages/docenti/docenti_26_27.markdown` e `_pages/direttivo/direttivo_26_27.markdown`

### 7.1 Pagina Docenti

**File**: `_pages/docenti/docenti_26_27.markdown`

**Percorso**: `_pages/docenti/docenti_26_27.markdown`

**Cosa fare**: Creare una nuova pagina Markdown per visualizzare il corpo docente dell'edizione 2026-2027.

**Contenuto del file**:
```markdown
---
layout: people
title: "Corpo Docente"
permalink: /docenti/26-27/
header_type: sbd
header_img: assets/images/header.svg
header_title: " "
data_source: docenti_26_27
data_type: docenti
description: "Il corpo docente del Master in Big Data Analytics è composto da professori, ricercatori e professionisti di grande esperienza nei settori del data mining, machine learning, big data analytics e intelligenza artificiale."
---
```

**Elementi del front matter**:
- `layout: people` - Layout per visualizzare persone (filtra automaticamente per `role: "Docente"`)
- `title` - Titolo della pagina
- `permalink` - URL della pagina (formato: `/docenti/YY-YY/`)
- `data_source` - Nome del file dati YAML docenti (senza estensione)
- `data_type: docenti` - Tipo di dati (serve per filtrare solo i docenti, escludendo il direttivo)
- `description` - Descrizione meta per SEO

### 7.2 Pagina Direttivo

**File**: `_pages/direttivo/direttivo_26_27.markdown`

**Percorso**: `_pages/direttivo/direttivo_26_27.markdown`

**Cosa fare**: Creare una nuova pagina Markdown per visualizzare il consiglio direttivo dell'edizione 2026-2027.

**Contenuto del file**:
```markdown
---
layout: direttivo
title: "Consiglio Direttivo 2026-2027"
permalink: /direttivo/26-27/
header_type: sbd
header_img: assets/images/header.svg
header_title: " "
data_source: docenti_26_27
---
```

**Elementi del front matter**:
- `layout: direttivo` - Layout specifico per il consiglio direttivo (filtra automaticamente per `role: "Direttore del Master"`, `"Vice-Direttrice"`, `"Consiglio Direttivo"`)
- `title` - Titolo della pagina (includere l'anno)
- `permalink` - URL della pagina (formato: `/direttivo/YY-YY/`)
- `data_source` - Nome del file dati YAML docenti (senza estensione, stesso file dei docenti)

**Nota importante**: Sia la pagina docenti che la pagina direttivo utilizzano lo stesso `data_source` (`docenti_26_27`), ma vengono filtrati automaticamente dai rispettivi layout in base al campo `role`:
- Layout `people` con `data_type: docenti` → mostra solo `role: "Docente"`
- Layout `direttivo` → mostra solo `role: "Direttore del Master"`, `"Vice-Direttrice"`, `"Consiglio Direttivo"`

---

## 9. Aggiornamento delle Scadenze Importanti

### File: `_data/master_info.json`

**Percorso**: `_data/master_info.json`

**Cosa fare**: Aggiornare il campo `scadenze` con le date importanti per la nuova edizione.

**Struttura di una scadenza**:
```json
{
  "voce": "Iscrizioni",
  "data": "2026-07-20",
  "data_fine": "2026-10-15",
  "data_label": "20 Luglio 2026",
  "data_fine_label": "15 Ottobre 2026",
  "numero_rata": null,
  "importo": null
}
```

**Campi disponibili**:
- `voce` (obbligatorio): Descrizione della scadenza (es. "Iscrizioni", "Pagamento Rata 1", "Lezioni")
- `data` (obbligatorio): Data di inizio in formato YYYY-MM-DD
- `data_fine` (opzionale): Data di fine in formato YYYY-MM-DD (se applicabile)
- `data_label` (obbligatorio): Label visualizzato (es. "20 Luglio 2026")
- `data_fine_label` (opzionale): Label per la data di fine
- `numero_rata` (opzionale): Numero della rata (per pagamenti rateali)
- `importo` (opzionale): Importo della rata in euro (es. "900")

**Scadenze tipiche per una nuova edizione** (esempio per 2026-2027):
```json
{
  "voce": "Iscrizioni",
  "data": "2026-07-20",
  "data_fine": "2026-10-15",
  "data_label": "20 Luglio 2026",
  "data_fine_label": "15 Ottobre 2026"
},
{
  "voce": "Pagamento Rata 1 (1.800 €)",
  "data": "2026-11-03",
  "data_label": "03 Novembre 2026",
  "numero_rata": 1,
  "importo": "1800"
},
{
  "voce": "Lezioni",
  "data": "2026-11-13",
  "data_fine": "2027-07-31",
  "data_label": "13 Novembre 2026",
  "data_fine_label": "31 Luglio 2027"
}
```

**Note importanti**:
- Le scadenze sono visualizzate nella pagina di iscrizione (`contatti.markdown`)
- La funzione `getStatoScadenza()` determina automaticamente lo stato di una scadenza (aperta, chiusa, prossima)
- Mantenere coerenza tra le date nel file master_info.json e quelle comunicate ufficialmente

---

## 8. Aggiornamento Informazioni Generali

### File: `_data/master_info.json`

**Percorso**: `_data/master_info.json`

**Cosa fare**: Aggiornare le informazioni generali del master per riflettere la nuova edizione.

**Campi da aggiornare**:

```json
{
  "edizione": "2026-2027",  // <-- Aggiornare l'edizione corrente
  "stats": [
    {
      "label": "Edizioni Master",
      "value": "13"  // <-- Incrementare il numero di edizioni (era 12, diventa 13)
    },
    {
      "label": "Studenti Laureati",
      "value": "272"  // <-- Aggiornare con il totale cumulativo (aggiungere laureati 2025-2026)
    },
    {
      "label": "Percentuale Assunti",
      "value": "97%"  // <-- Aggiornare se ci sono nuove statistiche
    },
    {
      "label": "Tempo Medio Assunzione",
      "value": "1.5 mesi"  // <-- Aggiornare se ci sono nuove statistiche
    },
    {
      "label": "Aziende Partner",
      "value": "54"  // <-- Aggiornare se ci sono nuovi partner
    },
    {
      "label": "Progetti Realizzati",
      "value": "56"  // <-- Incrementare con i nuovi progetti
    }
  ],
  "info_generali": {
    // ... resto delle informazioni
  }
}
```

**Dettaglio statistiche da aggiornare**:

1. **Edizioni Master**: Incrementare di 1 (da 12 a 13)
2. **Studenti Laureati**: Sommare i laureati dell'edizione 2025-2026 al totale precedente
3. **Percentuale Assunti**: Ricalcolare in base ai dati aggiornati di placement
4. **Tempo Medio Assunzione**: Aggiornare se ci sono nuovi dati disponibili
5. **Aziende Partner**: Aggiungere eventuali nuovi partner
6. **Progetti Realizzati**: Aggiungere i progetti dell'edizione 2025-2026

**Altre sezioni nel file da verificare**:
- `info_generali`: Date di inizio/fine, modalità di erogazione
- `requisiti`: Eventuali aggiornamenti ai requisiti di ammissione
- `costi`: Aggiornamento delle informazioni su tasse e costi
- `scadenze`: Date importanti per l'edizione 2026-2027

### 10. Checklist Finale

## 7. Checklist Finale

Prima di pubblicare la nuova edizione, verificare che:

### File Creati ✓
- [ ] `_data/didattica/didattica_26_27.yml` - Creato e popolato con tutti i corsi
- [ ] `_pages/didattica/didattica_26_27.markdown` - Creato con il front matter corretto
- [ ] `_data/studenti/studenti_26_27.yml` - Creato (anche solo con placeholder iniziale)
- [ ] `_pages/studenti/studenti_26_27.markdown` - Creato con il front matter corretto
- [ ] `_data/docenti/docenti_26_27.yml` - Creato e popolato con docenti e direttivo
- [ ] `_pages/docenti/docenti_26_27.markdown` - Creato con il front matter corretto
- [ ] `_pages/direttivo/direttivo_26_27.markdown` - Creato con il front matter corretto
- [ ] Cartella `assets/images/studenti/26_27/` - Creata per le future foto studenti
- [ ] Eventuali nuove immagini docenti in `assets/images/docenti/` - Se ci sono nuovi docenti

### File Modificati ✓
- [ ] `_data/edizioni.yml` - Aggiunta nuova edizione 2026-2027 in prima posizione
- [ ] `_data/edizioni.yml` - Impostato `active: true` per 2026-2027
- [ ] `_data/edizioni.yml` - Impostato `active: false` per 2025-2026
- [ ] `_data/master_info.json` - Aggiornato `edizione` a "2026-2027"
- [ ] `_data/master_info.json` - Incrementate le statistiche (edizioni, studenti, progetti)

### Verifica Coerenza ✓
- [ ] Il `data_source` in `docenti_26_27.markdown` corrisponde al nome del file docenti
- [ ] Il `data_source` in `direttivo_26_27.markdown` corrisponde al nome del file docenti (stesso file)
- [ ] Tutti i corsi nel file didattica hanno i campi obbligatori compilati
- [ ] Tutti i docenti hanno i campi obbligatori compilati (name, role, institution, bio, image)
- [ ] I membri del consiglio direttivo hanno il `role` corretto ("Direttore del Master", "Vice-Direttrice", "Consiglio Direttivo")
- [ ] I docenti ordinari hanno `role: "Docente"`ata/didattica/`
- [ ] Il `permalink` in `didattica_26_27.markdown` corrisponde all'`url` in `edizioni.yml`
- [ ] Verificare che la pagina `/docenti/26-27/` sia accessibile
- [ ] Verificare che la pagina `/direttivo/26-27/` sia accessibile
- [ ] Controllare che il selettore di edizioni mostri correttamente 2026-2027
- [ ] Verificare che l'edizione 2026-2027 sia marcata come "Edizione Corrente"
- [ ] Verificare che la pagina docenti mostri solo i docenti (role: "Docente")
- [ ] Verificare che la pagina direttivo mostri solo il consiglio direttivo
- [ ] Controllare che tutte le immagini dei docenti siano visualizzate correttament
- [ ] Tutti i corsi nel file didattica hanno i campi obbligatori compilati
- [ ] Controllare che tutte le immagini dei docenti siano visualizzate correttamente
- [ ] Eseguire `bundle exec jekyll serve` per testare il sito in locale
- [ ] Verificare che la pagina `/didattica/26-27` sia accessibile
- [ ] Verificare che la pagina `/studenti/26-27/` sia accessibile
- [ ] Controllare che il selettore di edizioni mostri correttamente 2026-2027
- [ ] Verificare che l'edizione 2026-2027 sia marcata come "Edizione Corrente"
- [ ] Controllare che non ci siano errori 404 o link rotti
- [ ] Verificare che le statistiche nella homepage siano aggiornate

### Contenuti da Aggiornare Successivamente
- [ ] Popolare `studenti_26_27.yml` con i dati reali degli studenti iscritti
- [ ] Aggiungere le foto degli studenti in `assets/images/studenti/26_27/`
- [ ] Aggiornare le informazioni sui docenti se ci sono cambiamenti
- [ ] Aggiornare la lista dei partner se ci sono nuove aziende
- [ ] Aggiungere eventuali nuovi progetti nella sezione progetti

---

## Note Aggiuntive

### Modifica della Home Page

La home page del master (`_pages/index.markdown`) utilizza il layout `master-home` e non necessita di aggiornamenti per ogni nuova edizione, poiché:
- Mostra le statistiche globali da `_data/master_info.json` (numero edizioni, studenti, etc.)
- Contiene la sezione "Evento Inaugurazione" che può essere aggiornata manualmente
- I CTA (Call To Action) rimangono stabili tra le edizioni

**Quando aggiornare il contenuto della home**:
- Per cambiamenti nel programma o nei dettagli del master
- Quando ci sono nuove sezioni o componenti da aggiungere
- Quando l'evento inaugurazione cambia luogo, data o modalità

### Gestione dei Partner

Il file `_data/partners.yml` contiene l'elenco dei partner aziendali. Questo file:
- È condiviso tra tutte le edizioni
- Non necessita di aggiornamenti frequenti (solo quando si aggiungono nuovi partner)
- Viene visualizzato nella pagina partner (`partner.markdown`)

**Struttura di un partner**:
```yaml
- name: "Nome Azienda"
  logo: "/assets/images/partners/logo.png"
  website: "https://www.azienda.com"
  description: "Breve descrizione dell'azienda e della collaborazione con il master"
```

### Gestione dei Progetti

Il file `_data/progetti.yml` contiene l'elenco dei progetti realizzati dagli studenti. Questo file:
- Contiene progetti da tutte le edizioni (campo `anno_accademico`)
- Viene visualizzato nella pagina progetti (`progetti.markdown`)
- Deve essere aggiornato al termine di ogni edizione con i nuovi progetti

**Struttura di un progetto**:
```yaml
- title: "Titolo del Progetto"
  anno_accademico: "2025-2026"
  descrizione: "Descrizione dettagliata del progetto"
  studenti: ["Nome Studente 1", "Nome Studente 2"]
  azienda_partner: "Nome Azienda Partner"
  tags: ["big data", "machine learning", "analisi"]
```

### Contenuti Rimossi e Deprecated

A febbraio 2026, sono state rimosse le seguenti pagine e componenti non più utilizzate:
- **Pagine**: `bootstrap.markdown`, `installation.markdown`, `jekyll-ssg.markdown`, `kramdown.markdown`, `markdown.markdown`, `obiettivi.markdown`, `single.markdown`
- **Snippets**: Frammenti di documentazione tecnica relativi a implementazione interna e design pattern
- **Componenti**: Diversi componenti HTML custom non più integrati nei layout (modal, selector, etc.)

Se in futuro è necessario recuperare questi contenuti, controllare la cronologia Git nei commit precedenti al 3 Febbraio 2026.

### Funzionalità Dinamiche Introdotte

#### 1. Gestione Dinamica delle Scadenze
La funzione `getStatoScadenza()` (localizzata in uno dei file JavaScript) determina automaticamente lo stato di una scadenza:
- **APERTA**: La data di iscrizione è ancora aperta
- **IN CORSO**: La scadenza è attualmente in corso
- **CHIUSA**: La scadenza è scaduta
- **PROSSIMA**: La scadenza è prossima

Il file `_data/master_info.json` contiene tutte le scadenze che verranno visualizzate dinamicamente nella pagina di iscrizione.

#### 2. Layout Consiglio Direttivo
Il nuovo layout `direttivo` filtra automaticamente i docenti in base al ruolo (`role`):
- Visualizza solo i membri con `role: "Direttore del Master"`, `"Vice-Direttrice"`, `"Consiglio Direttivo"`
- Viene utilizzato dalla pagina `_pages/direttivo/direttivo_YY_YY.markdown` per ogni edizione

#### 3. Filtro Layout People
Il layout `people` supporta il campo `data_type` per filtrare i dati:
- **`data_type: docenti`**: Mostra solo le persone con `role: "Docente"`
- **`data_type: studenti`**: Mostra solo i dati relativi agli studenti
- Questo permette di usare lo stesso data source per pagine diverse

### Tempistiche Suggerite

1. **Settembre-Ottobre**: Preparare i file base (didattica, struttura)
2. **Novembre**: Aggiornare con i dati degli studenti iscritti
3. **Durante l'anno**: Aggiornare progetti e altre informazioni dinamiche
4. **Fine anno**: Preparare le statistiche per l'edizione successiva

### Convenzioni di Naming

Il sito utilizza convenzioni consistenti per i nomi dei file:
- Anno accademico nel formato `YY_YY` (underscore) per i file: `didattica_26_27.yml`
- Anno accademico nel formato `YY-YY` (trattino) per gli URL: `/didattica/26-27`
- Anno accademico nel formato `YYYY-YYYY` per le label visualizzate: "2026-2027"

### Backup

Prima di apportare modifiche significative:
1. Creare un backup del repository
2. Lavorare su un branch separato (es: `feature/edizione-26-27`)
3. Testare accuratamente in locale
4. Fare merge solo dopo aver verificato che tutto funzioni correttamente

### Documentazione Tecnica

Il sito è costruito con:
- **Jekyll**: Generatore di siti statici
- **Liquid**: Template engine per i layout
- **YAML**: Formato per i file di dati
- **Markdown**: Formato per il contenuto delle pagine

Per maggiori informazioni consultare la [documentazione ufficiale di Jekyll](https://jekyllrb.com/docs/).

---

## Supporto

Per domande o problemi:
- Consultare il README principale del progetto
- Verificare la documentazione di Jekyll
- Controllare i file delle edizioni precedenti come riferimento
- Testare sempre in locale prima di pubblicare
