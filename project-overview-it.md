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

## Redesign Attuale (Fase MVP)

Il redesign porta un'interfaccia moderna e pulita con un'esperienza utente migliorata. Il nuovo sito è costruito con Vue e Nuxt con contenuti basati su markdown, distribuito su Cloudflare Pages.

Il progetto è attualmente nella fase **MVP (Minimum Viable Product)**, focalizzato sulla funzionalità principale e sulla creazione di una base solida per futuri miglioramenti.

---

## Prossimi Passi e Cosa Deve Essere Fatto

### Migrazione dei Contenuti

- **Importare Tutte le Notizie**: Migrare tutti gli articoli di notizie dal sito originale con proper mapping degli URL
- **Integrazione Blog**: Estrarre i contenuti da WordPress utilizzando WordPress API e visualizzarli con Nuxt/Vue, oppure implementare una strategia headless CMS
- **Aggiornamenti delle Informazioni**: Rivedere e aggiornare i contenuti del sito web esistente per accuratezza e completezza

### Team e Gestione dei Contenuti

- **Accesso del Team**: Configurare i member del team con accesso per gestire i contenuti
- **Integrazione CMS Futura**: Pianificare l'integrazione con una soluzione CMS headless nella Fase 2 per consentire ai member del team non tecnici di gestire i contenuti senza richiedere conoscenze di markdown

### Fasi Future

- Integrazione CMS headless per una gestione dei contenuti più semplice
- Implementazione di strumenti SEO (Google Search Console, sitemap, schema markup)
- Analytics e tracking (Google Analytics, cookie consent)
- Protezione da spam con Cloudflare (Bot Management/Turnstile)
- Integrazione mappe interattive (Mapbox o Google Maps con API keys appropriate)

---

**Ultimo Aggiornamento**: Giugno 2026  
**Stato**: MVP - Sviluppo Attivo
