# 📘 Guida Operativa & Manuale di Design: Progetto Fitness Lecco Club

> **Versione:** 1.0  
> **Oggetto:** Workflow Git/GitHub, Architettura Layout, Tipografia, Colori e Design Visivo (Dark Neon Mode)  
> **Destinazione:** Guida di riferimento rapida per lo sviluppo web del club  

---

## 📋 Indice dei Contenuti
1. [Workflow Git & Gestione Repository (Senza Errori)](#1-workflow-git--gestione-repository-senza-errori)
2. [Gestione Account Multipli e Autenticazione (Token PAT)](#2-gestione-account-multipli-e-autenticazione-token-pat)
3. [Layout della Pagina & Allineamenti Spaziali](#3-layout-della-pagina--allineamenti-spaziali)
4. [Tipografia & Scelta dei Font (Typography System)](#4-tipografia--scelta-dei-font-typography-system)
5. [Palette Colori & Teoria del Colore (Dark Premium & Neon Red Palette)](#5-palette-colori--teoria-del-colore-dark-premium--neon-red-palette)
6. [Design Visivo, Dettagli Decorativi & UI/UX](#6-design-visivo-dettagli-decorativi--uiux)
7. [Guida all'Avvio dei Progetti (Statico vs Node.js/React)](#7-guida-allavvio-dei-progetti-statico-vs-nodejsreact)
8. [Cheat Sheet dei Comandi e delle Regole d'Oro](#8-cheat-sheet-dei-comandi-e-delle-regole-doro)

---

## 1. Workflow Git & Gestione Repository (Senza Errori)

Per evitare conflitti, errori di `remote origin already exists` o `Repository not found`, segui la procedura standard corretta.

### A. Clonare una Repository Esistente (Il metodo più pulito)

**NON creare manualmente la cartella del progetto.** Lascia che sia Git a crearla automaticamente.

```bash
# 1. Spostati nella cartella principale (es. Desktop)
cd ~/Desktop

# 2. Clona la repository usando l'URL con Token integrato
git clone https://IL_TUO_TOKEN@github.com/r-46n0/fitness-lecco-club.git

# 3. Entra nella cartella appena creata
cd fitness-lecco-club
```

### B. Inizializzare un Progetto Locale Esistente

Se hai già i file sul computer e vuoi collegarli a una nuova repository vuota su GitHub:

```bash
# 1. Inizializza la cartella come repository Git
git init

# 2. Aggiungi tutti i file al tracking
git add .

# 3. Crea il primo commit
git commit -m "feat: primo commit prototipo fitness lecco club"

# 4. Imposta il branch principale su main
git branch -M main

# 5. Collega la repository remota (sostituisci IL_TUO_TOKEN)
git remote add origin https://IL_TUO_TOKEN@github.com/r-46n0/fitness-lecco-club.git

# 6. Invia i dati su GitHub
git push -u origin main
```

---

## 2. Gestione Account Multipli e Autenticazione (Token PAT)

### Perché la password standard non funziona più?
GitHub ha disabilitato l'autenticazione tramite password da terminale. È obbligatorio usare un Personal Access Token (PAT) o la configurazione SSH.

### Come Generare un Token PAT in 30 Secondi:
1. Vai su GitHub.com → Clicca sull'immagine profilo → **Settings**.
2. Scorri in fondo a sinistra → **Developer Settings** → **Personal Access Tokens** → **Tokens (classic)**.
3. Clicca su **Generate new token (classic)**.
4. Nome: `Macbook-Dev-FitnessLecco` | Scadenza: `90 giorni` o `No Expiration`.
5. Spunta la casella principale **repo** (concede il controllo completo dei repository).
6. Clicca **Generate token** e copia la stringa generata (inizia con `ghp_...`).

### Risoluzione Errori Frequenti:

| Errore nel Terminale | Causa Radice | Soluzione Immediata |
| :--- | :--- | :--- |
| `fatal: remote origin already exists.` | La cartella ha già un'origine configurata. | `git remote remove origin` oppure `git remote set-url origin <URL>` |
| `remote: Repository not found.` | Account o URL non corretti / Mancanza di permessi. | Verificare l'utente e reinserire il Token remoto. |
| `remote: Invalid username or token.` | Credenziali salvate nel Portachiavi scadute o errate. | Aggiornare l'URL remoto col nuovo Token. |

---

## 3. Layout della Pagina & Allineamenti Spaziali

Per un club fitness immersivo e ad altissima energia, la struttura visiva deve combinare spazi ampi, contrasto elevato e sezioni a forte impatto visivo.

### A. La Regola della Griglia a 8px (8pt Grid System)
Tutti i margini, padding e dimensioni delle schede/corsi devono essere multipli di 8px (oppure 4px per dettagli come i bordi neon):
- Padding interno componenti: `12px`, `16px`, `24px`, `32px`
- Margine tra sezioni principali: `64px`, `96px`, `128px`

### B. Gestione del Layout e Responsive
- **Larghezza Contenitore Massimo (Container Max-Width):**
  - Schede Corsi / Tabella Orari: `1100px`
  - Layout Web Standard & Hero Section: `1280px` - `1400px`
- **Allineamento Visivo:**
  - Layout a griglia dinamica per le schede dei corsi ed eventi.
  - Titoli hero centrati o con testo d'impatto allineato a sinistra su grafiche dello skyline di Lecco.

```css
/* Layout Base Dark Mode & High Contrast */
.container {
  width: 100%;
  max-width: 1280px;
  margin-left: auto;
  margin-right: auto;
  padding-left: 20px;
  padding-right: 20px;
}

.section-dark {
  background-color: #0A0A0A;
  padding-top: 96px;
  padding-bottom: 96px;
}
```

---

## 4. Tipografia & Scelta dei Font (Typography System)

Il settore fitness richiede una tipografia monumentale, aggressiva e dinamica nei titoli, abbinata a font ultra-leggibili e tecnologici per palinsesti ed orari.

### Pairings di Font Ufficiali
- **Stile High Energy & Performance (Scelta Principale)**
  - **Heading (Titoli & Accenti):** Bebas Neue o Montserrat Extra Bold Condensed (Sans-Serif Condensed, imponente, energico, maiuscolo)
  - **Body (Testo & Palinsesti):** Inter o Outfit / Chakra Petch (Geometria pulita, ad altissima leggibilità su schermi OLED/AMOLED)

### Gerarchia Tipografica Consigliata

```css
:root {
  /* Font Families */
  --font-heading: 'Bebas Neue', 'Montserrat', sans-serif;
  --font-body: 'Inter', system-ui, -apple-system, sans-serif;

  /* Scale Tipografica */
  --text-hero: clamp(3rem, 7vw, 5.5rem);   /* Titoli Monumentali */
  --text-h1: clamp(2.2rem, 4.5vw, 3.5rem); /* 35px - 56px */
  --text-h2: clamp(1.6rem, 3vw, 2.2rem);   /* 25px - 35px */
  --text-h3: 1.35rem;                      /* 21px */
  --text-body: 1rem;                       /* 16px */
  --text-small: 0.875rem;                  /* 14px */
  
  /* Line Height & Spaziatura */
  --lh-heading: 1.05;                      /* Interlinea compatta per impatto visivo */
  --lh-body: 1.6;
  --ls-heading: 1.5px;                     /* Spaziatura lettere per titoli maiuscoli */
}
```

---

## 5. Palette Colori & Teoria del Colore (Dark Premium & Neon Red Palette)

I colori del Fitness Lecco Club trasmettono energia, tecnologia ed esclusività. La base è dominata da un nero profondo spezzato da bagliori rosso neon e accenti oro/giallo.

### Palette Ufficiale "Fitness Lecco Club"

| Ruolo | Colore | Codice HEX | Descrizione Visiva |
| :--- | :--- | :--- | :--- |
| **Sfondo Principale** | Obsidian Black | `#0A0A0A` / `#000000` | Nero profondo per un'esperienza immersiva Dark Mode. |
| **Superfici / Card** | Dark Charcoal Glass | `#141414` / `rgba(20,20,20,0.8)` | Schede semi-trasparenti scure con effetto vetro satinato. |
| **Testo Principale** | Pure White | `#FFFFFF` | Bianco puro ad altissimo contrasto su sfondo scuro. |
| **Accento Principale** | Pulsing Neon Red | `#FF0033` / `#FF1E38` | Rosso neon per elementi attivi, bottoni e tracciato ECG. |
| **Accento Secondario** | Club Gold | `#E5A93C` / `#FFC700` | Giallo/Oro elegante derivato dal badge "CLUB" del logo. |
| **Bordi & Glow Effect**| Neon Subtle Glow | `rgba(255,0,51,0.25)` | Bagliore luminoso sottile per bordi ed elementi in hover. |

```css
:root {
  --bg-main: #0A0A0A;
  --bg-card: #141414;
  --text-primary: #FFFFFF;
  --text-muted: #A1A1AA;
  --accent-neon: #FF0033;
  --accent-gold: #E5A93C;
  --border-neon: rgba(255, 0, 51, 0.3);
  --glow-red: 0 0 20px rgba(255, 0, 51, 0.4);
}
```

---

## 6. Design Visivo, Dettagli Decorativi & UI/UX

I dettagli dell'interfaccia riflettono lo stile visivo del canale Instagram: impatto neon, skyline di Lecco ed elementi cardiaci.

### A. Elementi Decorativi per il Club

**Effetto Glassmorphism Scuro:** Schede con sfondi scuri semi-trasparenti e sfocatura `backdrop-filter`:

```css
.card-neon {
  background: rgba(20, 20, 20, 0.85);
  backdrop-filter: blur(12px);
  border: 1px solid var(--border-neon);
  border-radius: 12px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.card-neon:hover {
  transform: translateY(-4px);
  border-color: var(--accent-neon);
  box-shadow: var(--glow-red);
}
```

**Badge d'Impatto & Linea ECG Neon:**
Inserisci sopra i titoli delle sezioni dei badge ripresi dalla comunicazione del brand:

```html
<span class="badge-neon">NOVITÀ A LECCO</span>
<h2 class="title-monumental">UNA NUOVA DIMENSIONE DEL FITNESS</h2>
```

---

## 7. Guida all'Avvio dei Progetti (Statico vs Node.js/React)

Quando sviluppi o aggiorni una sezione del sito web, identifica l'architettura tecnica in uso:

### Caso A: Sito Statico (HTML, CSS/Tailwind, JS)
1. Apri la cartella del progetto.
2. Avvia con l'estensione **Live Server** su VS Code (tasto destro su `index.html` → *Open with Live Server*).

### Caso B: Web App / Progetto Node.js (React, Vite, Next.js)
1. Verifica la presenza del file `package.json`.
2. Apri il terminale ed esegui i comandi:

```bash
# 1. Scarica i moduli e le dipendenze mancanti
npm install

# 2. Avvia il server locale di sviluppo
npm run dev
```

---

## 8. Cheat Sheet dei Comandi e delle Regole d'Oro

### 🔴 I 3 Errori da NON Fare Mai Più:
1. **NON** usare mai sfondi chiari o bianchi piatti. Il sito deve mantenere una visuale Dark Mode Premium.
2. **NON** abusare dell'effetto bagliore neon. Usa il bagliore (`--glow-red`) solo per stati attivi, bottoni d'azione principali e hover, evitando il sovraccarico visivo.
3. **NON** creare manualmente la cartella prima del `git clone` e usa sempre il Token PAT (`ghp_...`).

### ⚡ Prontuario Comandi Rapidi:

```bash
# Salvare e Spingere le modifiche in 3 passaggi
git add .
git commit -m "feat: aggiunta sezione corsi e layout neon"
git push

# Ripristino URL remoto con Token corretto
git remote remove origin
git remote add origin https://IL_TUO_TOKEN@github.com/r-46n0/fitness-lecco-club.git
```

---
*Guida generata per il team di sviluppo — Progetto Fitness Lecco Club.*