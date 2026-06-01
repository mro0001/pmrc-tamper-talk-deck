# TaMPERing Generative AI — Slide Decks

Browser-based [reveal.js](https://revealjs.com/) versions of the **TaMPER** talk
(Task · Model · Prompt · Evaluation · Reporting — a framework for the systematic and
responsible use of LLMs), styled to match the
[evaluation presentation](../../evaluation_presentation/).

**Authors:** Michael Overton · Barrie Robison · Luke Sheneman — University of Idaho (IIDS / RCDS).

## The two decks

| File | Slides | What it is |
|------|--------|------------|
| `docs/slides-tamper-talk.html` | 48 | The clean pedagogical talk: technical intro → TaMPER framework → conclusion. |
| `docs/slides-tamper-reference.html` | 60 | The reference edition: the same framework preceded by the empirical model-comparison results section. |

Both were converted from the original PowerPoint sources in `~/Documents/Research/Tamper/`
(`Tampering.pptx` and `Tampering For Eric Reference.pptx`).

## How it was built

- **Text/bullet slides** were re-authored into the evaluation presentation's HTML
  component vocabulary (`title-a`, `slide-card`, `pillar-grid`, `slide-kicker`, styled `cite`s).
- **Images, charts, and SmartArt** are embedded *as they appear in the original* — each was
  rendered from PowerPoint via LibreOffice (`soffice --headless --convert-to pdf` →
  `pdftoppm`) and placed full-bleed on a clean figure slide. The rendered per-slide PNGs
  live in `docs/img/<deck>/slides/`.
- `slides.css` and the vendored `reveal/` engine are copied verbatim from the evaluation
  presentation; `tamper.css` carries that deck's inline component styles plus a few
  TaMPER-specific additions (the acronym reveal, section dividers, full-image helper).
- `source_extracts/` holds the raw per-slide text dumps and the full PDF/PNG renders
  (provenance + a fidelity reference).

## Run locally

```bash
cd "pmrc Tamper slide deck"
python3 -m http.server 4173 -d docs
```

Then open:

- <http://127.0.0.1:4173/slides-tamper-talk.html>
- <http://127.0.0.1:4173/slides-tamper-reference.html>

Arrow keys (or the on-screen controls) navigate. Press `f` for fullscreen, `o` for the
slide overview, `?` for the full keymap.

## Print to PDF

Append `?print-pdf` to a slide URL and use the browser's print dialog (`Cmd-P`). Reveal.js
renders one slide per page in this mode.

## Known fidelity note

The original PowerPoint slides use **build animations** (content appears step by step).
LibreOffice flattens all animation states onto a single rendered page, so a few image
slides show two overlapping title lines or a fully-built diagram where the original
revealed it progressively. The re-authored text slides (titles, dividers, the TaMPER
acronym, card grids) are unaffected. If a specific image slide needs a clean single-state
render, export it from PowerPoint/Keynote and drop the PNG into `docs/img/<deck>/slides/`.

## Attribution

- Technical scaffolding (`slides.css`, vendored reveal.js) is lifted from
  [`ui-insight/REACHWorkshop2026`](https://github.com/ui-insight/REACHWorkshop2026)
  (Wiggins, Layman, Robison — UI Insight, University of Idaho), reused with attribution.
- reveal.js is © Hakim El Hattab and contributors, MIT license.
- The substance of these decks — content, examples, and the TaMPER framework — is original
  to Overton, Robison, and Sheneman.
