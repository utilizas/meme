# Memes and the Philosophy of Digital Phenomena
### *Viral Culture as Epistemic Infrastructure?*

**Authors:** Miguel Moreno (Universidad de Granada) · A. Claude et al. (Anthropic PBC)<sup>*</sup>  
**Date:** *circa* March 2026  
**Format:** Quarto HTML monograph · Dual light/dark theme · APA 7 citations

---

## Overview

A scholarly monograph in the intersection of memetics, epistemology, philosophy of
technology, and Science and Technology Studies (STS). The text examines internet memes
not as ephemeral cultural debris but as constitutive infrastructure for collective
knowledge formation in networked societies — with the Chuck Norris Facts (2005–present)
as the primary case study.

This work operates in two explicit registers: rigorous academic argument and
productive epistemic irony. Sections marked with amber **Epistemic Irony** panels
perform critical analysis through humour rather than despite it — a methodological 
choice whose rationale is developed in the text.

---

## Project Structure

```
.
├── meme-epistemology.qmd      # Main document (source)
├── references.bib             # Bibliography (APA 7)
├── apa.csl                    # Citation style (APA 7th edition)
├── styles-light.scss          # Light theme (base: cosmo)
├── styles-dark.scss           # Dark theme (base: darkly)
├── _meta-tags.html            # HTML head: OG, Twitter Card, Dublin Core, JSON-LD
├── og-image.png               # Social preview image (1200×630)
├── ogimage.png                # In-document cover image
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
```bash
quarto render meme-epistemology.qmd
```

Output: `index.html` in the project root.

## Deployment

The monograph is deployed at:

- [GitHub Pages](https://utilizas.github.io/meme/) (canonical)
- [Vercel](https://meme-mocha-six.vercel.app/)
- [Netlify](https://memeti.netlify.app/)

---

## Citation

Archived at [Zenodo](https://doi.org/10.5281/zenodo.19277505) with DOI `10.5281/zenodo.19277505`.
```bibtex
@misc{moreno2026memes,
  author    = {Moreno Mu{\~n}oz, Miguel},
  title     = {Memes and the Philosophy of Digital Phenomena:
               Viral Culture as Epistemic Infrastructure?},
  year      = {2026},
  month     = mar,
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.19277505},
  url       = {https://doi.org/10.5281/zenodo.19277505},
  note      = {HTML monograph, CC BY-NC-SA 4.0}
}
```

## Licence

© 2026 Miguel Moreno.   
Text and original analysis: [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)  
Cited works remain the property of their respective authors and publishers.  
Meme templates and viral artefacts discussed are the property of their respective
creators; their inclusion constitutes fair dealing for the purposes of criticism,
commentary, and academic research.

---

## Acknowledgements

Source materials include three documents circulated as inspiration for this project:  
The first is a journalistic retrospective on the Chuck Norris meme phenomenon published by Bastarrica (2026) in Digital Trends upon the actor’s death in March 2026. The second is Didyme-Dôme (2026), a Rolling Stone obituary that recontextualises Norris’s cultural afterlife by situating the meme economy within a broader narrative of celebrity durability and late‑career mythopoesis. The third is an anonymous satirical Tratado sobre el “Big Bang” de la Memética Moderna — a parody academic paper that, beneath its pantomime rigour, encodes several genuine insights into the structural mechanics of viral diffusion. 

All three are cited where analytically relevant, which is more often than one might expect.

---

<sup>*</sup> *The et al. in the second author attribution refers, with appropriate literalness,
to the training corpus.*
