# Progetto Infra - Redesign del Sito Web

## Panoramica del Progetto

Questo progetto è un completo redesign e modernizzazione del sito web [infrascan.net](https://www.infrascan.net/). L'obiettivo è portare il servizio di scansione dell'infrastruttura e della sicurezza esistente in un'interfaccia moderna e user-friendly mantenendo la funzionalità principale della piattaforma originale.

**Deployment Attuali:**
- Sito principale: [infra-36j.pages.dev](https://infra-36j.pages.dev/)
- Produzione: [infrascan.net](https://www.infrascan.net/)

---

## Architettura del Sito Originale

### Sito Principale (infrascan.net)
Il sito originale è un'applicazione web tradizionale costruita con:
- **Sicurezza**: reCAPTCHA per la protezione dei moduli
- **Performance**: Cloudflare Rocket Loader per la distribuzione ottimizzata degli asset
- **Rete**: Supporto HTTP/3
- **Frontend**: Framework UI Bootstrap 4.1.1 con jQuery 3.3.1
- **CDN**: Cloudflare per la distribuzione dei contenuti e la sicurezza

### Piattaforma Blog (blog.infrascan.net)
Un blog basato su WordPress che supporta contenuti multilingue:

**Lingue Supportate:**
- Olandese
- Inglese
- Francese
- Tedesco
- Italiano
- Russo
- Spagnolo
- Catalano
- Vietnamita

---

## Redesign Attuale (MVP)

### Obiettivi
Il redesign si concentra sulla modernizzazione dell'esperienza utente e dell'interfaccia mentre stabilisce una piattaforma scalabile e mantenibile per il futuro:

1. **UX/UI Moderno**: Completo redesign visivo e di interazione con pattern di design contemporaneo
2. **Architettura Basata su Contenuti**: Gestione dei contenuti basata su Markdown per una manutenzione più semplice
3. **Generazione di Siti Statici**: Distribuzione come pagine statiche su Cloudflare Pages per prestazioni e affidabilità migliori
4. **Infrastruttura Scalabile**: Base per future integrazioni con soluzioni CMS headless
5. **Gestione degli Asset**: Archiviazione R2 connessa per la gestione efficiente dei media

### Stack Tecnologico

#### Framework Principale
- **Nuxt 3**: Framework Vue full-stack per la costruzione dell'applicazione
- **Vue 3**: Architettura UI basata su componenti

#### Gestione dei Contenuti
- **Markdown**: Formato di contenuto principale per tutte le pagine e i post del blog
- **@nuxt/content**: Livello di integrazione della gestione dei contenuti per l'elaborazione markdown

#### Styling e Design
- **Tailwind CSS**: Framework CSS utility-first per lo sviluppo rapido e responsive dell'UI

#### Funzionalità Aggiuntive
- **Mapbox GL**: Per mappe interattive e funzionalità basate sulla posizione
- **TypeScript**: Sviluppo type-safe in tutta l'applicazione

#### Deployment e Infrastruttura
- **Cloudflare Pages**: Hosting statico con deployment automatici
- **Cloudflare R2**: Archiviazione di oggetti per immagini, documenti e altri asset

---

## Stato Attuale: Fase MVP

Il progetto è attualmente nella fase **MVP (Minimum Viable Product)** con le seguenti caratteristiche:

### ✅ Completati
- Redesign moderno dell'UI/UX del sito principale
- Struttura e setup dell'applicazione Nuxt 3
- Pipeline di gestione dei contenuti basata su Markdown
- Configurazione del deployment su Cloudflare Pages
- Integrazione R2 per l'archiviazione degli asset
- Design responsive su tutti i dispositivi
- Configurazione TypeScript e type safety

### 🚧 In Corso / Pianificati

#### Migrazione dei Contenuti
- **Importazione Notizie**: Migrare gli articoli di notizie esistenti dal sito originale con proper mapping degli URL e reindirizzamenti
- **Integrazione Blog**: Importare i post del blog da WordPress con metadati e categorie mantenuti
- **Preservazione degli URL**: Garantire reindirizzamenti SEO-friendly dai vecchi URL alla nuova struttura dei contenuti

#### Integrazione CMS
Il progetto è progettato per funzionare inizialmente con markdown, con integrazione pianificata di soluzioni CMS headless:
- **Opzioni in Valutazione**:
  - PageCMS
  - SveltiaCMS
  - DecapCMS
- **Timeline**: Fase 2 del progetto
- **Scopo**: Consentire ai member del team non tecnici di gestire i contenuti senza editing diretto del markdown

#### Aggiornamenti dei Contenuti
- Revisione e aggiornamento dei contenuti del sito web esistente
- Garantire l'accuratezza delle informazioni tecniche
- Modernizzare il linguaggio e il tono
- Aggiungere informazioni mancanti dal sito originale

#### Funzionalità Migliorate (Future)
- Funzionalità di ricerca su tutti i contenuti
- Filtraggio avanzato per notizie e risorse
- Sistema di account utente (se necessario)
- Integrazione analytics
- Integrazione social media

---

## Struttura del Progetto

```
infra/
├── app.vue                 # Componente applicazione root
├── nuxt.config.ts          # Configurazione Nuxt
├── tsconfig.json           # Configurazione TypeScript
├── tailwind.config.ts      # Configurazione Tailwind CSS
│
├── pages/                  # Route pagine (auto-generate)
├── components/             # Componenti Vue riutilizzabili
├── layouts/                # Template layout pagine
├── composables/            # Composable Vue riutilizzabili
├── content/                # File di contenuto Markdown
├── assets/                 # Asset statici (immagini, font, ecc.)
├── public/                 # Asset pubblici (robots.txt, favicon, ecc.)
└── types/                  # Definizioni di tipo TypeScript
```

---

## Come Iniziare

### Installazione
```bash
npm install
```

### Server di Sviluppo
```bash
npm run dev
```
Accedi al sito su `http://localhost:3000`

### Build per la Produzione
```bash
npm run build
```

### Genera Sito Statico
```bash
npm run generate
```
Crea file statici ottimizzati pronti per il deployment su Cloudflare Pages.

### Preview Build di Produzione
```bash
npm run preview
```

---

## Workflow di Gestione dei Contenuti

### Aggiunta di Articoli di Notizie
1. Crea un nuovo file markdown nella directory `content/`
2. Includi metadati (titolo, data, categoria, ecc.) nel frontmatter
3. Scrivi il contenuto in formato markdown
4. Commit e push delle modifiche (auto-deploy tramite Cloudflare Pages)

### Aggiunta di Pagine
1. Crea un nuovo componente `.vue` nella directory `pages/`
2. Riferisci ai contenuti markdown dalla directory `content/` se necessario
3. Deploy automatico al commit

### Gestione degli Asset
1. Carica immagini e documenti su Cloudflare R2
2. Riferisci agli URL di R2 nei contenuti markdown o nei componenti
3. Sfrutta la CDN di R2 per la distribuzione globale

---

## Deployment

### Cloudflare Pages
- **Deploy Automatici**: Connesso al repository, esegue il deploy ad ogni push
- **Preview per Branch**: Le pull request generano deployment di preview
- **Dominio di Produzione**: infrascan.net tramite DNS gestito da Cloudflare

### Variabili di Ambiente
Configurazione memorizzata nel file `.env` (le credenziali non vengono commit nel repository)

---

## Prossimi Passi e Priorità

### Fase 1 (MVP Attuale - In Corso)
- [ ] Completare la migrazione dei contenuti dal sito originale
- [ ] Importare tutti i post del blog con categorizzazione appropriata
- [ ] Stabilire la strategia di reindirizzamento degli URL
- [ ] Aggiornare l'accuratezza e la completezza dei contenuti

### Fase 2 (Q3 2026)
- [ ] Integrare un CMS headless per la gestione dei contenuti
- [ ] Configurare l'accesso del team al CMS senza richiedere competenze tecniche
- [ ] Aggiungere funzionalità di ricerca
- [ ] Integrazione analytics

### Fase 3 (Q4 2026)
- [ ] Filtraggio e categorizzazione avanzati
- [ ] Funzionalità di engagement degli utenti (commenti, newsletter)
- [ ] Ottimizzazione delle prestazioni
- [ ] Framework di A/B testing

---

## Note Tecniche

### Elaborazione Markdown
Il modulo `@nuxt/content` elabora automaticamente i file markdown con:
- **YAML Frontmatter**: Estrazione dei metadati
- **Syntax Highlighting**: I blocchi di codice sono evidenziati automaticamente
- **Indice dei Contenuti**: Auto-generato dalle intestazioni
- **Validazione dei Link**: I link non validi possono essere rilevati durante il build

### Integrazione Cloudflare
- **R2 per Asset**: Fornisce archiviazione di oggetti compatibile con S3
- **Pages per Hosting**: Piattaforma di deployment connessa a Git
- **CDN**: Distribuzione globale automatica degli asset statici
- **Sicurezza**: Protezione DDoS e SSL/TLS per impostazione predefinita

---

## Contatti e Contributi

Per domande sull'architettura del progetto o per contribuire al redesign, contatta il team di sviluppo.

---

**Ultimo Aggiornamento**: Giugno 2026  
**Stato**: MVP - Sviluppo Attivo  
**Manutentori**: Team di Sviluppo
