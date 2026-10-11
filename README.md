# PaletteCraft

A color, value, and historical pigment studio for painters and visual artists. Analyzes painterly color palettes, authentic pigments, proportional color masses, and 10-step tonal value structures from classical masterpieces and custom artwork studies.

**Live Studio:** [https://mugglebornpadawan.github.io/palete-craft/](https://mugglebornpadawan.github.io/palete-craft/)

---

## Visual Arts Studio Features

### 1. Archival Matting & Ambient Contrast
- **Preserved Aspect Ratios:** Artworks display uncropped within dynamic archival matting.
- **Ambient Studio Contrast:** Uses warm archival linen (`#E8E3DC`) for high and mid-key compositions. Automatically shifts to deep gallery charcoal (`#1C1A17`) for low-key chiaroscuro works (e.g., Vermeer) to prevent glare and preserve delicate shadow glazes (*velatura*).
- **Curated Classical Art Presets:** Katsushika Hokusai (*The Great Wave* — ukiyo-e woodblock), Vincent van Gogh (*The Starry Night* — tube impasto), Claude Monet (*Water Lilies* — broken color scumble), Johannes Vermeer (*Girl with a Pearl Earring* — tenebrist glaze).
- **Museum Provenance & Medium Attribution:** Institutional attribution, historical paint medium specifications, and Public Domain worldwide licensing status.
- **Studio Easel:** Place your own painting studies and reference photos for instant, private client-side color and value analysis.

### 2. Color, Value & Pigment Analysis
- **Color Mass & Dominance (Focal-Weighted):** Visualizes canvas mass distribution as a proportional ribbon. Uses saturation weighting ($1.0 + 1.8 \times S$) so vital focal accents (such as Hokusai's vermilion seal or Vermeer's pearl highlight) maintain compositional prominence rather than vanishing in flat area math.
- **Masstone & Undertone Swatch Drawdowns:** Two-tier test cards displaying pure opaque paint body (masstone) alongside translucent glaze washes revealing the substrate (undertone).
- **Historical Pigment Approximation:** Algorithmic mapping of extracted tones to authentic artist pigments (*Prussian Blue / Bero-ai*, *Genuine Lapis Lazuli*, *French Ultramarine*, *Alizarin Crimson*, *Mineral Vermilion*, *Yellow Ochre*, *Chrome Yellow*, *Deep Viridian*, *Lead White*, *Bone Black*). Monet's palette accurately excludes earth pigments (*Terre Verte*, umber) and black.
- **10-Step Tonal Value Scale:** Evaluates value structure from Value 1 (deep shadow / bone black) to Value 10 (high highlight / lead white). Classifies works into Low-Key (deep shadow / chiaroscuro), Mid-Key (harmonized), or High-Key (luminous).
- **Color Temperature Balance:** Quantifies the exact ratio of Cool vs. Warm pigments across the composition.
- **Harmony & Paint Handling:** Separates chromatic color schemes (*Analogous*, *Complementary Nocturne*, *Harmonic Spectrum*) from physical paint application (*Ukiyo-e Bokashi Gradation*, *Directional Impasto Flow*, *Broken Color Scumble*, *Tenebrist Glazing*).
- **Painterly Fallbacks:** Procedural rendering simulating historical techniques when photographic reproductions are offline.
- **Pure Browser Atelier:** Single-file HTML5 Canvas and vanilla JavaScript. Runs offline without build dependencies.

---

## Project Structure

```text
palete-craft/
├── assets/
│   ├── hokusai.jpg          # Katsushika Hokusai — The Great Wave
│   ├── pearl_earring.jpg    # Johannes Vermeer — Girl with a Pearl Earring
│   ├── starry_night.jpg     # Vincent van Gogh — Starry Night
│   └── water_lilies.jpg     # Claude Monet — Water Lilies
├── index.html               # Main studio application & fine-art color engine
└── README.md                # Project documentation
```

---

## Quick Start

### Direct Browser Opening
Open `index.html` directly in your browser:
```bash
firefox index.html
```

### Local HTTP Server
Run a local static server using Babashka:
```bash
bb http-server
```
*(Serving over HTTP ensures canvas pixel sampling is not blocked by strict browser `file://` policies).*

---

## Atelier Analytical Architecture

* **Spatial Pixel Sampling:** Samples pixels at 2px intervals to capture delicate highlights and broad washes.
* **Focal Mass Weighting:** Balances spatial coverage against chromatic saturation ($1.0 + 1.8 \times S$) to ensure critical focal accents (such as Vermeer's pearl highlight or Hokusai's vermilion seal) receive true compositional prominence.
* **Tonal Value Scale:** Computes relative luminance ($Y = 0.2126R + 0.7152G + 0.0722B$) mapped across a 10-step Munsell value scale (Value 1: Bone Black shadow to Value 10: Lead White highlight).
* **Historical Pigment Heuristics:** Maps HSV coordinates and tonal values to authentic historical artist pigments with medium-conscious constraints.

---

## Preset Assets & Licensing

All preset artworks located in the `assets/` directory are faithful photographic reproductions of two-dimensional historic paintings. Both the original artworks and these digitizations are in the **Public Domain** worldwide.

| Image Asset | Title & Artist | Year | Source / Institution | Rights Status |
| :--- | :--- | :--- | :--- | :--- |
| `assets/hokusai.jpg` | *The Great Wave off Kanagawa*<br>Katsushika Hokusai (1760–1849) | c. 1831 | Metropolitan Museum of Art / Wikimedia Commons | **Public Domain** (`PD-Art`, `PD-US-expired`) |
| `assets/starry_night.jpg` | *The Starry Night*<br>Vincent van Gogh (1853–1890) | 1889 | Museum of Modern Art / Google Art Project via Wikimedia Commons | **Public Domain** (`PD-Art`, `PD-US-expired`) |
| `assets/water_lilies.jpg` | *Water Lilies* (*Nymphéas*)<br>Claude Monet (1840–1926) | c. 1916 | Google Art Project via Wikimedia Commons | **Public Domain** (`PD-Art`, `PD-US-expired`) |
| `assets/pearl_earring.jpg` | *Girl with a Pearl Earring*<br>Johannes Vermeer (1632–1675) | c. 1665 | Mauritshuis, The Hague / Wikimedia Commons | **Public Domain** (`PD-Art`, `PD-old-100`) |

> [!NOTE]
> Under international copyright law and legal precedent (*Bridgeman Art Library v. Corel Corp.*), exact two-dimensional photographic reproductions of public domain artworks do not create new copyright. They remain free for all cultural, educational, and commercial uses.

---

## Privacy & Studio Ownership

### 1. 100% Private Client-Side Studio (Zero Server Uploads)
* **Local In-Memory Execution:** All user-uploaded painting studies are processed entirely within the local web browser using HTML5 FileReader and Canvas APIs.
* **Zero Remote Transmission:** No image files, pixel buffers, telemetry, or user metadata are ever uploaded, transmitted, or stored on any remote server, database, or external service.
* **Ephemeral State:** When the browser tab closes or reloads, all loaded image memory is immediately cleared.

### 2. User Ownership & Rights
* **Ownership Remains with the Artist:** PaletteCraft claims zero ownership over any images uploaded by artists or the derived palettes.
* **User Due Diligence:** Users are responsible for confirming usage rights and permissions for any third-party files they study.

---

## License

- **Software Code:** GPL-3.0-or-later.
- **Preset Artwork Digitizations:** Public Domain (`CC0` / `PD-Art`).


