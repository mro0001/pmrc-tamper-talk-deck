# Start Here — TaMPER Talk Deck

## What this is

The slide deck for Michael Overton's TaMPER talk at the PMRC 2026 pre-conference workshop, *Beyond the Hype: Using Generative AI in Public Administration Research* (American University, June 3 2026). It is the Block 2 framework session.

The deck teaches the **TaMPER framework** for using generative AI in public administration research with rigor. The letters are **T**ask, the silent **a**gents, **M**odel, **P**rompt, **E**valuation, **R**eporting. It is a browser-based reveal.js deck, styled to match Michael's LLM evaluation presentation. The goal is a talk that **demonstrates** with live, interactive examples rather than asserts, and that an audience of PA scholars can follow regardless of technical background.

## The deck and where things live

All paths below are inside `pmrc_conference_workshop_2026/pmrc Tamper slide deck/`.

| File | What it is |
| --- | --- |
| `docs/slides-tamper-talk.html` | The talk deck, 40 slides. This is the live deck. |
| `docs/slides-tamper-reference.html` | A longer reference edition (older structure, kept for material). |
| `docs/tamper.css` | Deck-specific styles, the type scale, components, and interactive pieces. |
| `docs/slides.css` | Shared styling copied from the evaluation deck. |
| `docs/img/`, `docs/reveal/` | Images and the vendored reveal.js engine. |
| `docs/judge_score_*.json` | Data the evaluation KDE charts load at runtime. |
| `SLIDE_TITLES.md` | The working slide map, used for revisions (see below). |
| `README.md` | How to run and print the deck, plus attribution. |

### View it

The deck must be served over http, not opened as a file (the interactive widgets and data charts need a server). From the deck folder:

```
python3 -m http.server 4173 -d docs
```

Then open http://127.0.0.1:4173/slides-tamper-talk.html. Arrow keys navigate, `f` is fullscreen, `?` shows the keymap, and adding `?print-pdf` to the URL plus the browser print dialog exports a PDF handout.

Seven slides are click-interactive (each marked in `SLIDE_TITLES.md`). They only work over the http server.

## How we revise the deck (the SLIDE_TITLES.md process)

`SLIDE_TITLES.md` is the simple, scannable map of every slide in order, grouped by section, with `(click)` marking the interactive ones. It is how we run a revision pass.

1. Open `SLIDE_TITLES.md` and write a note under any slide you want changed. Anything works, a sentence, the word "remove," "make this interactive," a full rewrite, or a question.
2. Tell me the file is updated.
3. I read your notes, make the changes in the deck, and verify each one by rendering the slide.
4. I regenerate `SLIDE_TITLES.md` so its numbers and titles match the new deck, and we go again.

This keeps feedback slide by slide and low effort. Whenever the deck changes (slides added, removed, reordered), the map is refreshed so it always mirrors the live deck.

## Supporting research and proposals

Background work for the deck lives one level up, in `pmrc_conference_workshop_2026/`.

- `tamper_paper_extracted.md` is the TaMPER paper, the source of truth for the framework.
- `deck_review_recommendations.md`, `eval_examples_and_gaps.md`, and `font_size_best_practices.md` are review passes against the evaluation deck.
- `agent_slides_proposal.md`, `model_section_proposal.md`, and `complexity_uncertainty_citations.md` are the research behind specific sections.
- `prompt_iteration_demo.md` holds the real model outputs behind the before and after prompt slide.
