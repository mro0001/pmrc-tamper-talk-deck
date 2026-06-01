# PMRC 2026 Intro Deck — Design

**Date:** 2026-05-31
**Source content:** `For introduction presentation.docx` (directives) + `Copy of Brainstorming Document - PMRC 2026.docx` (schedule outline)
**Style reference:** `docs/slides-tamper-talk.html` + `slides.css` + `tamper.css`

## Goal

A short standalone "introduction" presentation that opens the workshop, in the
exact visual style of the existing TaMPER talk deck.

## Decisions (confirmed with user)

1. **Packaging:** standalone new file `docs/slides-intro.html`, reusing the same
   `reveal/`, `slides.css`, and `tamper.css`. Runs as its own opener before the
   TaMPER talk. No new CSS is authored.
2. **Schedule:** revised after first build to a **vertical timeline agenda**
   (dot markers as bullets, continuous rail) showing session title, presenter,
   and start time for each block, grouped Morning / Afternoon.
3. **Presenters:** circular headshots sit **above** each card (centered, gold
   ring); cards carry **hyperlinked names** to each main presenter's official
   bio page and **left-aligned** text; cards are equal height. Headshots:
   Overton (local `img/overton-headshot.jpg`), Stokan (ericjstokan.com), Larson
   (miamioh.edu profile). Marwa stays a text support line (no headshot/link).
4. **IS / IS NOT:** two separate slides (approved as presented in the slide map).
5. **Styling:** all new rules live in a **scoped `<style>` block inside
   `slides-intro.html`**; the shared `slides.css`/`tamper.css` are untouched.
   Slide copy avoids em-dashes and colons per user preference.
6. **Typography (per `font_size_best_practices.md`):** base lifted 24px -> 28px
   (Priority 1), scoped to this deck only so the main TaMPER deck is unaffected.
   Kickers 0.85em, silver-note 0.92em (darkened to #404040), citations 0.85em
   (Priority 2/3). Custom presenter/agenda classes were converted from `rem` to
   `em` so they anchor to the deck base and scale with it; previously `rem`
   anchored them to the 16px page root, rendering agenda text near 16px (below
   the 24px floor). `.pcard` text rules carry extra specificity to beat
   `.slide-card p`. Verified all 8 slides fit the 900px canvas after the bump.

## Reused style vocabulary

`title-a` (cover w/ gold stripe), `slide-kicker` (gold uppercase label),
`reveal h2`, `pillar-grid` + `slide-card` (gold/gray top-border cards),
`tdivider[data-letter]` (giant ghost letter divider), `closing-line` (italic
emphasis), `gold-rule`, `tamper-sub`, `headline-stat` / note box, `cite`.
reveal init copied verbatim from the talk deck (1600x900, no extra plugins).

## Slide map (8 slides)

1. **Title** — `title-a`. Kicker "PMRC 2026 · Pre-Conference Workshop 4"; H1
   "Beyond the Hype"; sub "Using Generative AI in Public Administration
   Research"; gold "Sponsored by IIDS" line as top item; date/venue
   (June 3, 2026 · American University, Washington, D.C.).
2. **Sponsorship** — IIDS named in full; note box "Paid for the pre-conference
   workshop? Email me — moverton@uidaho.edu."
3. **Presenters** — 3 cards (Overton/UIdaho, Stokan/UMBC, Larson/Miami OH) +
   support line for Marwa Elsayed (PhD student, UIdaho).
4. **Schedule** — vertical timeline agenda. Morning (Welcome 10:00; Foundations
   of GenAI 10:20; Lunch 12:00) and Afternoon (TaMPER 1:00; Coding Lab 2:20;
   Synthesis 5:50), each row showing title, presenter, and start time.
5. **What this workshop IS** — 3 gold cards: build basic understanding of
   GenAI; understand its use in research; work through real examples.
6. **What this workshop is NOT** — 3 gray cards: not how to write papers with
   GenAI; not a sales pitch for AI; not a forum for extended
   practical/political/ethical debate (ethics session excepted).
7. **Group activity** — `tdivider`-style prompt: take 2–5 minutes and write
   down what you want out of this workshop.
8. **Discussion** — big centered question "What do you want out of this
   workshop?" for the share-out.

## Presenter titles (researched; user to sanity-check)

- **Michael Overton** — Associate Professor of Public Administration; Associate
  Director, Institute for Interdisciplinary Data Science; University of Idaho.
- **Eric Stokan** — Associate Professor of Political Science; Director, Center
  for Social Science Scholarship; UMBC. (Dept bio narrates 2018 hire as
  assistant; current sources show Associate + Elkins Professorship 2025.)
- **Sarah Larson** — Associate Professor, Political Science / Center for Public
  Management and Regional Affairs; Miami University (Oxford, Ohio).
- **Marwa Elsayed** — PhD student, University of Idaho (workshop support).

7. **Layout / whitespace:** reveal `center` set to **false**; every non-title
   section is instead flex-centered within a fixed `min-height` (760px canvas
   units) via `display:flex !important` (beats reveal's inline `display:block`)
   + `align-items:stretch` (keeps full-width card grids full width). This
   balances leftover space top/bottom and holds the heading at a consistent
   position. Persistent chrome: an 8px gold left edge stripe and a slim bottom
   footer ("Beyond the Hype · PMRC 2026 Pre-Conference Workshop 4"), both
   `position:fixed`. The sparse "scope" slides (`What it is` / `is not`) use
   tall 300px cards with a gold check / gray cross icon and top-aligned content
   so the row fills the slide instead of leaving an empty band; the title slide
   keeps its own full-height `title-a` layout.

## Out of scope

No new images, no edits to the existing talk deck, no reveal plugin additions.
