# Memes and the Philosophy of Digital Phenomena
### *Viral Culture as Epistemic Infrastructure?*

**Authors:** Miguel Moreno Muñoz (Universidad de Granada) · A. Claude et al. (Anthropic PBC)<sup>*</sup>
**Date:** *circa* March 2026  
**Format:** Quarto HTML monograph · Dual light/dark theme · APA 7 citations

---

## Overview

A scholarly monograph in the intersection of memetics, epistemology, philosophy of
technology, and Science and Technology Studies (STS). The text examines internet memes
not as ephemeral cultural debris but as constitutive infrastructure for collective
knowledge formation in networked societies — with the Chuck Norris Facts (2005–present)
as the primary case study.

The monograph operates in two explicit registers: rigorous academic argument and
productive epistemic irony. Sections marked with amber **Epistemic Irony** panels
perform critical analysis through humour rather than despite it. This is not a stylistic
choice; it is a theoretical commitment documented in the text itself.

---

## Project Structure

```
.
├── meme-epistemology.qmd      # Main document (source)
├── references.bib             # Bibliography (57+ entries, APA 7)
├── apa.csl                    # Citation style (APA 7th edition)
├── styles-light.scss          # Light theme (base: cosmo)
├── styles-dark.scss           # Dark theme (base: darkly)
├── _meta-tags.html            # HTML head: OG, Twitter Card, Dublin Core, JSON-LD
└── README.md                  # This file
```

> **Note:** `apa.csl` is not included in the repository.  
> Download from the [Zotero CSL repository](https://github.com/citation-style-language/styles/blob/master/apa.csl)
> and place in the project root before rendering.

---

## Dependencies

### Required

| Tool | Version | Notes |
|------|---------|-------|
| [Quarto](https://quarto.org) | ≥ 1.4 | Rendering engine |
| R + `knitr` | ≥ 4.3 | Optional; only required if R code chunks are added |
| `apa.csl` | — | Download separately (see above) |

### Fonts (loaded via Google Fonts CDN)

- **Cormorant Garamond** — body text
- **Playfair Display** — headings
- **Lora** — humor panels
- **JetBrains Mono** — code, meme-facts, labels
- **Inter** — UI elements, metadata, TOC

No local font installation required; the SCSS imports them at render time.
For offline rendering, download the fonts and update the `@import url(...)` lines
in both SCSS files accordingly.

---

## Rendering

### Local render

```bash
# Clone or download the project, then:
cd meme-epistemology
quarto render meme-epistemology.qmd
```

Output: `meme-epistemology.html` in the project root.

### Preview with live reload

```bash
quarto preview meme-epistemology.qmd
```

## Deployment

The rendered output is a single self-contained HTML file. Any static hosting service
will serve it correctly. The options below are listed in approximate order of
configuration simplicity.

### Cloudflare Pages

1. Push repository to GitHub or GitLab.
2. In Cloudflare Pages dashboard: **Create a project → Connect to Git**.
3. Build settings:
   - **Build command:** `quarto render meme-epistemology.qmd`
   - **Build output directory:** `/` (root)
   - **Environment variable:** `QUARTO_VERSION=1.4.555` (or later)
4. Cloudflare Pages will install Quarto automatically via the build environment.
5. Custom domain: configure in **Custom domains** tab.

> Cloudflare Pages provides free SSL, global CDN, and permanent deployment URLs
> at `https://[project].pages.dev`. Recommended for academic deployment.

### Netlify

1. Push repository to GitHub.
2. In Netlify dashboard: **Add new site → Import an existing project**.
3. Build settings:
   - **Base directory:** (leave blank)
   - **Build command:** `quarto render meme-epistemology.qmd`
   - **Publish directory:** `.` (root)
4. Add a `netlify.toml` in the project root for reproducibility:

```toml
[build]
  command = "quarto render meme-epistemology.qmd"
  publish = "."

[build.environment]
  QUARTO_VERSION = "1.4.555"
```

5. Custom domain: configure in **Domain management**.

### Vercel

1. Push repository to GitHub.
2. In Vercel dashboard: **Add New Project → Import Git Repository**.
3. Framework preset: **Other**.
4. Build settings:
   - **Build command:** `quarto render meme-epistemology.qmd`
   - **Output directory:** `.`
   - **Install command:** `curl -LO https://quarto.org/download/latest/quarto-linux-amd64.deb && dpkg -i quarto-linux-amd64.deb`
5. Add a `vercel.json` in the project root:

```json
{
  "buildCommand": "quarto render meme-epistemology.qmd",
  "outputDirectory": ".",
  "installCommand": "curl -LO https://quarto.org/download/latest/quarto-linux-amd64.deb && dpkg -i quarto-linux-amd64.deb"
}
```

> Vercel's free tier has a 45-second build time limit. The monograph renders in
> approximately 20–35 seconds on a standard build runner.

### GitHub Pages (simplest option)

1. Render locally: `quarto render meme-epistemology.qmd`
2. Push the rendered `meme-epistemology.html` (and rename to `index.html`) to the
   `gh-pages` branch, or configure GitHub Pages to serve from the `main` branch root.
3. Enable GitHub Pages in repository **Settings → Pages**.
4. Alternatively, use the official Quarto GitHub Actions workflow:

```yaml
# .github/workflows/publish.yml
on:
  push:
    branches: [main]

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: quarto-dev/quarto-actions/publish@v2
        with:
          target: gh-pages
```

### Zenodo (permanent archival DOI)

For a citable, permanently archived version with a DOI:

1. Render locally and verify the output.
2. Create a `.zenodo.json` in the project root:

```json
{
  "title": "Memes as Epistemic Infrastructure: Viral Culture, Knowledge Transmission, and the Philosophy of Digital Phenomena",
  "creators": [
    {
      "name": "Moreno Muñoz, Miguel",
      "affiliation": "Universidad de Granada",
      "orcid": "0000-0002-0746-9587"
    },
    {
      "name": "Claude, A. et al.",
      "affiliation": "Anthropic PBC"
    }
  ],
  "description": "A scholarly monograph examining internet memes as constitutive infrastructure for collective knowledge formation in networked societies.",
  "access_right": "open",
  "license": "cc-by-4.0",
  "keywords": ["memetics", "epistemology", "digital culture", "philosophy of technology", "STS", "Chuck Norris Facts"],
  "language": "eng",
  "upload_type": "publication",
  "publication_type": "other"
}
```

3. Upload the rendered HTML and source files to [zenodo.org](https://zenodo.org).
4. The DOI will be minted on publication and is citable in APA 7 as:

```
Moreno Muñoz, M., & Claude, A. et al. (2026). Memes as epistemic infrastructure:
Viral culture, knowledge transmission, and the philosophy of digital phenomena.
Zenodo. https://doi.org/10.5281/zenodo.XXXXXXX
```

---

## Citation

```bibtex
@misc{moreno2026memes,
  author    = {Moreno Mu{\~n}oz, Miguel and {Claude, A. et al.}},
  title     = {Memes as Epistemic Infrastructure: Viral Culture,
               Knowledge Transmission, and the Philosophy of
               Digital Phenomena},
  year      = {2026},
  note      = {HTML monograph. \textit{c.} March 2026},
  url       = {[DEPLOYMENT_URL]}
}
```

---

## Licence

Text and original analysis: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)  
Cited works remain the property of their respective authors and publishers.  
Meme templates and viral artefacts discussed are the property of their respective
creators; their inclusion constitutes fair dealing for the purposes of criticism,
commentary, and academic research.

---

## Acknowledgements

Source materials include two documents circulated as inspiration for this project:
a journalistic retrospective on the Chuck Norris phenomenon published by @bastarrica2026
in *Digital Trends*, and an anonymous satirical *Tratado sobre el "Big Bang" de la
Memética Moderna* — a parody academic paper that, beneath its pantomime rigour,
encodes several genuine insights into the structural mechanics of viral diffusion.

Both are cited where analytically relevant, which is more often than one might expect.

---

*The et al. in the second author attribution refers, with appropriate literalness,
to the training corpus.*
