# Quire V1

## Differenze V0 e V1

La V0 è basata su Hugo, la V1 su Eleventy (11ty), il primo era in go, il secondo in javascript.
Eleventy permette di creare degli shortcode collegati a dei components.

## Appunti V1.0.0-rc16 (usata Gallerie Estensi)

### Staging Cbox
- http://gale.dev-box.it:12080/
- http://192.168.1.120:8080/

### Camel Case

Non si può usare il camelcase nelle cassi e negli id perchè lo spiana

### Bottoni sulla scheda

- Non c'è uno shortcode nativo per i bottoni
- viene supportato solo il bottone "View in collection" se in objects.yaml viene settato l'attributo link. Il testo del bottone può essere
  configurato in config.yml file.

### Viewer IIIF integrato

Per utilizzare il viewer iiif integrato, le figure vanno settate con i seguenti parametri di Jarvis

- manifestId: https://gallerie-estensi.jarvis.memooria.org/meta/iiif/d4f00875-8bca-4596-861b-1393d987e2d6/manifest
- canvasId: https://gallerie-estensi.jarvis.memooria.org/meta/iiif/d4f00875-8bca-4596-861b-1393d987e2d6/canvas/57f4d4bb-9607-46fd-baea-553d8f79bb6f

https://github.com/thegetty/quire/discussions/703

## Personalizzazioni Gallerie Estensi

#### Riferimenti
Dati Jarvis:
https://gallerie-estensi.jarvis.memooria.org/meta/culturalItems/618a5d08748f0856ea023e38

Visore Jarvis Dzi:
https://gallerie-estensi.jarvis.memooria.org/images/viewers/dzi/?culturalItemUuid=52693a93-67d7-4b52-b665-840502868945&customUIName=gallerie-estensi

Figma
https://www.figma.com/file/7t4xk7PvRqR7Iu12vKmF81/Catalogo-Estense---Quire-customisation?type=design&node-id=0%3A1&t=Hvt2JSrYu3uRP1An-1

Drive:
https://drive.google.com/drive/folders/1v5mJCMmrfyj3qO384n-Rv86gNwLaNHDL?usp=sharing

#### Font
- titoli: bebas neue
- testi: fira sans

#### Configurazione dati

- /content/_data/config.yaml (parametri di configurazione)
  - defaultLocale: it-it
  - menuType: brief
  - nextButtonText: Avanti
  - prevButtonText: Indietro
- /content/_data/objects.yaml
  - object_display_order:
    - artista
    - title
    - datazione
    - supporto
    - dimensioni
    - collocazione
    - inventario
    - iscrizioni timbri
- publication.yaml (dati della pubblicazione)
  - URL DELLA PUBBLICAZIONE:    /content/_data/publication.yaml
- FIGURES: /content/_data/figures.yaml

### Front-End

#### File modificati:
content/_assets/javascript/application/index.js --> Aggiunto import al file custom.js
content/_assets/javascript/custom.js --> aggiunto il contenuto
content/_assets/styles/colors.scss --> Aggiunti due colori
content/_assets/styles/application.scss --> modifiche annotate nei commenti con //memooria o // memooria
content/_assets/styles/variables.scss --> modifiche annotate nei commenti con //memooria o // memooria

#### File aggiunti:
content/_assets/styles/fonts.scss --> aggiunto
content/_assets/fonts/Bebas_Neue --> aggiunta la cartella del font con i relativi files
content/_assets/fonts/Fira_Sans --> aggiunta la cartella del font con i relativi files
content/_assets/images/logo-gallerie-estensi.png --> aggiunto

#### Note:
Il file content/_assets/styles/custom.css viene importato di default

## Attivazione Jarvis

Abbiamo innestato la logica che mostra il visore nel file:
_includes/components/figure/image/canvas-panel.js
Per attivare questo componente è necessario che la figure di testata abbia l'attributo "zoom" settato a true ed l'attributo "jarvis"
settato con i link del visore.

canvas-panel.js:
- Riceve i dati da figures.yaml
- In figures.yaml avevamo aggiunto un attributo jarvis alle immagini
- Canvas-panel.js avevamo aggiunto un attributo data-jarvis alle


## Readme originale

The [Quire Eleventy package](https://github.com/thegetty/quire/tree/main/packages/11ty) contains configuration and modules for the [Eleventy static site generator](https://11ty.dev). This package is published to npm as [`@thegetty/quire-11ty`](https://www.npmjs.com/package/@thegetty/quire-11ty) and installed by the [`@thegetty/quire-cli`](https://www.npmjs.com/package/@thegetty/quire-cli) to build [Quire](https://quire.getty.edu) projects.

### Quire Eleventy Features

#### Components and Shortcodes

Component-driven page templates using [shortcode components](https://github.com/thegetty/quire/tree/main/packages/11ty/_includes/components) and [universal template shortcodes](https://www.11ty.dev/docs/shortcodes/#universal-shortcodes) that support [JavaScript](https://www.11ty.dev/docs/languages/javascript/), [Liquid](https://www.11ty.dev/docs/languages/liquid/), [Nunjucks](https://www.11ty.dev/docs/languages/nunjucks/), and [WebC](https://www.11ty.dev/docs/languages/webc/) templates.

#### Image Processing

Automatic processing of images as [IIIF](https://iiif.io) assets.

#### PDF Output

Generates HTML output for generation of PDF books using [`Paged.js`](https://pagedjs.org)

#### EPUB Output

Generates HTML output for generation of EPUB book using [`EPUB.js`](http://futurepress.org)