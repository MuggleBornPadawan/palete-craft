# PaletteCraft

Fine Art Gallery & Brand Identity System that extracts harmonized 5-token brand color palettes and generates proportional geometric brand marks from historic masterpieces and custom artwork uploads.

---

## Perspectives & Features

### 1. Fine Art Gallery
- **Masterpiece Exhibition:** Curated classical art presets (*The Great Wave off Kanagawa*, *The Starry Night*, *Water Lilies*, *Girl with a Pearl Earring*).
- **Uncropped Gallery Matting:** Artwork displayed with museum-grade containment matting preserving original composition and aspect ratio.
- **Museum Provenance:** Full exhibition metadata with institution attribution and worldwide Public Domain licensing status.
- **Custom Artwork Curation:** Upload custom imagery for instant client-side palette extraction.

### 2. Brand Design Tool
- **Semantic Brand Tokens:** Extracts 5 distinct, harmonized color tokens assigned to concrete design system roles (`Dominant`, `Secondary`, `Accent`, `Surface`, `Neutral`).
- **Proportional Geometric Brand Mark:** Derives a vector-ratio geometric brand mark (50% hero block + 4 balanced accent quadrants) from the extracted palette.
- **Live Brand System Preview:** Real-time design system mockup (cards, primary CTAs, outline buttons, and badge chips) that dynamically recolors on token selection.
- **One-Click Clipboard Copy:** Instant hex code copying to the clipboard with visual toast feedback.
- **Perceptual Color Engine:**
  - Chroma vividness scoring prioritizes vibrant brand swatches over muddy background tones.
  - Redmean perceptual distance ensures distinct contrast across all 5 selected tokens.
- **Zero Build Dependencies:** Single-file HTML5 Canvas and vanilla JavaScript. Runs offline without npm or node dependencies.

---

## Project Structure

```text
palete-craft/
├── assets/
│   ├── hokusai.jpg          # Katsushika Hokusai — The Great Wave
│   ├── pearl_earring.jpg    # Johannes Vermeer — Girl with a Pearl Earring
│   ├── starry_night.jpg     # Vincent van Gogh — Starry Night
│   └── water_lilies.jpg     # Claude Monet — Water Lilies
├── index.html               # Main application and color engine
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

## Technical Architecture

* **Quantization:** Samples pixels at 2px intervals and groups colors into 16-unit bins.
* **Vividness Scoring:** Filters out near-grayscale pixels and balances chroma against lightness.
* **Redmean Distance:** Calculates weighted color distance to maximize distinctness:
  $$\Delta C = \sqrt{\left(2 + \frac{\bar{r}}{256}\right)\Delta r^2 + 4\Delta g^2 + \left(2 + \frac{255 - \bar{r}}{256}\right)\Delta b^2}$$
* **Safe Canvas Scaling:** Limits internal canvas sampling to a maximum dimension of 400px to prevent memory bottlenecks.

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

## User Content & Privacy Clauses

### 1. Client-Side Only Processing (No Server Storage)
* **Local In-Memory Execution:** All custom user-uploaded images are processed entirely within the local web browser using the HTML5 FileReader and Canvas APIs.
* **Zero Remote Transmission:** No image files, pixel buffers, telemetry, or user metadata are transmitted, uploaded, or stored on any remote server, database, or external service.
* **Ephemeral State:** When the browser tab closes or reloads, all uploaded image memory is immediately cleared.

### 2. User Ownership & Rights Verification
* **Ownership Remains with the User:** PaletteCraft claims zero ownership over any images uploaded by users or the derived color schemes.
* **User Due Diligence:** Users are solely responsible for checking and confirming image copyright, intellectual property rights, licensing agreements, and usage permissions for any files they upload.

---

## License

- **Software Code:** GPL-3.0-or-later.
- **Preset Artwork Digitizations:** Public Domain (`CC0` / `PD-Art`).


