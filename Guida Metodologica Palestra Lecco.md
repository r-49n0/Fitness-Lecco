# 🏛️ Guida Metodologica per Prototipi Web — Fitness Lecco Club

## 1. Profilo e Identità del Brand
* **Descrizione del Cliente:** **Fitness Lecco Club**, un'esclusiva struttura fitness di nuova concezione con sede a Lecco. Posizionamento di alto impatto, moderno, immersivo e ad alta energia. Il target di riferimento è un pubblico dinamico, orientato alla performance, all'innovazione e al benessere, con un forte senso di appartenenza al territorio lecchese (lago e montagne).
* **Tono di Voce:** Emozionante, diretto, motivazionale e futuristico. Utilizzo di messaggi d'impatto brevi, evocativi ed incisivi (es. *"Novità a Lecco"*, *"Una Nuova Dimensione"*, *"Qualcosa di Unico ed Emozionante"*).
* **Identità Visiva:** Stile **Dark Mode Premium & High Contrast**. L'aspetto visivo sfrutta lo sfondo nero profondo (`#000000` / `#0A0A0A`) combinato con dettagli **Rosso Neon Pulsante** (`#FF0033` / `#FF1E38`) ed elementi di contrasto in **Bianco Puro** e lievi accenti **Giallo/Oro** (derivati dal badge *"CLUB"* del logo). La linea visiva fonde l'iconografia del territorio di Lecco (skyline della città, profilo delle montagne/Resegone e lago) con elementi di vitalità e frequenza cardiaca (linea ECG neon).

---

## 2. Tipografia e Timbro Visivo
* **Gerarchia dei Font:**
  * **Font Principale (Titoli e Accenti):** Font Sans-Serif Condensed ad altissimo impatto e carattere monumentale (es. *Bebas Neue*, *Anton* o *Montserrat Extra Bold Condensed*), utilizzato in maiuscolo con spaziatura definita per trasmettere potenza, grinta e presenza visiva.
  * **Font di Supporto (Testo e Navigazione):** Font Sans-Serif geometrico e futuristico (es. *Inter*, *Outfit* o *Chakra Petch*), ottimizzato per la massima leggibilità tecnica su dispositivi mobile e schermi ad alta risoluzione (OLED/AMOLED).
* **Trattamento dei Testi:** Titoli principali in maiuscolo monospaziato con effetti di luce o glow sottile per richiamare i neon; sottotitoli e testi descrittivi con formattazione fluida, buona spaziatura interlinea ed elevato contrasto su sfondo scuro per facilitare la consultazione rapida.

---

## 3. Elementi Decorativi e Micro-Interazioni
* **Sfondi e Sezioni Hero:** Sfondi scuri arricchiti da sfumature radiali rosso-drammatiche, bagliori neon soffusi (*glow effect*) e grafiche dinamiche che combinano la sagoma del paesaggio lecchese con tracciati di impulsi cardiaci in animazione d'onda fluida.
* **Dettagli d'Ambiente:** Schede e banner dotati di bordi illuminati in stile LED neon, sfondi semi-trasparenti con effetto vetro satinato scuro (*glassmorphism* scuro con `backdrop-blur`) per dare profondità tridimensionale ed evitare superfici piatte.
* **Transizioni ed Effetti:** Risposta visiva reattiva e "tecnologica" al passaggio del cursore (hover) o al tocco: pulsazione dell'intensità luminosa dei bordi neon, lievi ingrandimenti delle schede e variazioni di brillantezza sui bottoni d'azione principali (*Call to Action*).

---

## 4. Componenti Interattive Fondamentali
* **Vetrine e Contenuti in Evidenza (Hero Showcase):** Caroselli e sezioni d'impatto a tutto schermo con fotografie d'ambiente ad alto contrasto, sovrapposizioni visive scure, portal neon centrali e typography d'impatto che richiamano la campagna di lancio del club.
* **Modalità di Espansione (Lightbox & Experience Preview):** Possibilità di aprire schede descrittive di corsi, aree della palestra ed attrezzature in modalità pop-up dark full-screen, corredate da video teaser brevi in loop e dettagli d'ambiente.
* **Cataloghi e Schedule Dinamici:** Palinsesto orario dei corsi e listino servizi consultabili rapidamente tramite filtri per categoria (*Cardio*, *Strength*, *Functional*, *Personal Training*), con sistema di prenotazione o richiesta informazioni integrato in pochissimi tap.
* **Elementi di Riassunto e Social Proof:** Feed integrato del profilo Instagram in tempo reale, counter dinamici di membri della community e box recensioni firmati con il badge *"Fitness Lecco Approved"* per generare immediata fiducia ed hype.

---

## 5. Architettura delle Pagine e Struttura
* **Organizzazione Modulare:**
  * Architettura organizzata con cartelle chiare per le pagine (`/home`, `/corsi`, `/abbonamenti`, `/location-lecco`, `/contatti`) e moduli riutilizzabili per i componenti della GUI (`/components/neon-card`, `/components/hero-skyline`, `/components/schedule-picker`).
  * Separazione netta tra risorse mediatiche (`/assets/images`, `/assets/vectors/lecco-skyline.svg`) e file di configurazione stilistica.
* **Pulizia del Codice:** Mantenimento delle variabili di stile globali (palette colori neon `--neon-red`, `--dark-bg`, `--gold-accent`, regole per i bagliori) separate dalla struttura semantica HTML e dalle logiche interattive JS/TS.

---

## 6. Flusso di Lavoro e Gestione della Collaborazione
* **Isolamento dei File Temporanei:** Esclusione rigorosa dal tracciamento di versione (tramite `.gitignore`) di tutti i file generati da editor locali, risorse grafiche temporanee ad alta risoluzione non ottimizzate e configurazioni d'ambiente.
* **Procedura di Salvataggio Sicura:**
  1. Selezione controllata dei soli file di codice o asset vettoriali aggiornati per lo sviluppo del prototipo.
  2. Creazione di messaggi di salvataggio espliciti e strutturati (es. `feat: add neon skyline background and course filter`).
  3. Sviluppo coordinato su rami dedicati (`feature/dark-neon-theme`, `feature/interactive-schedule`) per non compromettere il codice stabile.
  4. Test e verifica della resa dei colori neon e dei contrasti su dispositivi mobili prima dell'integrazione sul ramo principale.
