# Tech for Good — techforgood.world

Sito Jekyll, pronto per GitHub Pages. Nessuna build locale richiesta: GitHub
costruisce il sito automaticamente a ogni push.

## 1. Crea il repository

1. Su GitHub, crea un nuovo repository (es. `techforgood.world`).
2. Carica tutto il contenuto di questa cartella nel repository (root del repo,
   non in una sottocartella).
3. Vai su **Settings → Pages** → in "Build and deployment" seleziona
   **Deploy from a branch**, branch `main`, cartella `/ (root)`.

## 2. Collega il dominio GoDaddy

**Su GitHub** (Settings → Pages → Custom domain): inserisci `techforgood.world`
(il file `CNAME` incluso qui lo fa già, ma confermalo anche nell'interfaccia).

**Su GoDaddy** (DNS Management del dominio):

| Tipo | Host | Valore |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | tuonomeutente.github.io |

Poi, su GitHub → Settings → Pages, attiva **Enforce HTTPS** (può richiedere
qualche ora dopo la propagazione DNS).

## 3. Aggiungere un nuovo articolo

Crea un file in `_posts/` con nome `AAAA-MM-GG-titolo-breve.md`:

```yaml
---
title: "Il titolo del tuo articolo"
categories: [digital-point-of-care]   # oppure tech-in-pharma / ai-powered-rd
read_time: 5
---

Il contenuto in Markdown...
```

L'articolo appare automaticamente in home, nell'archivio (`/articles/`) e
nella pagina del pilastro corrispondente.

## 4. Prima di pubblicare

- [ ] Sostituisci il link LinkedIn placeholder in `_includes/footer.html` e
      in `about.md` con il tuo profilo reale
- [ ] Rileggi i 3 articoli seed in `_posts/` — sono contenuti di esempio,
      pensati per mostrare tono e struttura, non testi definitivi
- [ ] Verifica su `preview.html` (apribile localmente nel browser, doppio
      click) l'aspetto della homepage prima del primo push

## Struttura

```
_config.yml         → impostazioni sito
_layouts/            → template HTML (home, post, pillar, page, archive)
_includes/            → header e footer
_posts/               → articoli (3 di esempio, uno per pilastro)
assets/css/main.css   → tutto lo stile del sito
assets/images/logo.svg → logo (polpo digitale)
index.md, about.md, articles.md → pagine principali
digital-point-of-care.md, tech-in-pharma.md, ai-powered-rd.md → pagine pilastro
preview.html          → anteprima statica, apribile senza Jekyll
```
