# TaMPER Talk Deck — Presentation Review

Reviewed 2026-05-31. Deck rendered slide by slide over a local server (38 slides, indices 0 to 37) and inspected as screenshots. Source of truth for accuracy checks is `tamper_paper_extracted.md` (arXiv:2504.01037). This file is the only thing edited; the deck itself was not touched.

---

## 1. Overall assessment

This is a strong, well-built deck. The TaMPER spine is clear, the visual system (gold accent, ghost section letters, kicker + H2 + closing line) is consistent and professional, and the interactive slides genuinely earn their place. The Evaluation section in particular delivers on "demonstrate, don't assert" with real worked tables (compliance, accuracy, precision) that walk the audience through the floor-clearing logic. The before/after prompt iteration slide and the use-case switcher are the kind of show-don't-tell moments the workshop wants.

What works:
- The acronym reveal (slides 2 to 3) and the "from gut feel to defensible" framing (slide 5) set up the whole talk economically.
- The Agents section is a genuinely good teaching arc: harness definition, then workflow-vs-AI, then wiring shapes, then the complexity-vs-uncertainty boundary.
- The Evaluation worked examples are the heart of the deck and they are excellent. The dependency logic (clear the floor, then move up) is communicated through the tables, not just stated.
- Consistent kicker / closing-line discipline across almost every content slide.

The biggest opportunities, in priority order:
1. **A real model-set inconsistency inside the Evaluation section** that an attentive PA methods audience will notice (the criteria tables and the KDE charts show different four-model line-ups). This is the most important fix because it undercuts the "auditable, reproducible" message the deck is selling.
2. **The "six decisions" framing fights the paper's "five decision points."** The deck repeatedly says six; the published framework says five (the sixth, Agents, is the deck's own silent-a addition). This is a deliberate choice but it is not flagged anywhere, and a reader who knows the paper will think the deck miscounted.
3. **Three house-style violations** (colons in rendered prose) and one **lowercase-sentence typo**, all easy fixes.
4. **A few density and layout problems** at projector distance: the PPI slide has label-text collisions, slide 7 packs three cards plus a four-column table, and several charts have hard-to-read rotated or tiny labels.
5. **Length.** 38 slides is a lot for one workshop block. There are 2 to 4 slides that can be cut or merged without losing the argument.

---

## 2. Top prioritized suggestions (the headline list)

1. **Reconcile the model set across the Evaluation section.** Slides 27, 28, 30 (compliance, accuracy, precision tables) use **Command A, GPT OSS, Phi 4, Qwen 3**. Slides 33 and 34 (KDE distributions) use **Command A, Gemma 3, GPT OSS, Phi 4** — Qwen 3 is dropped and Gemma 3 appears from nowhere. Same "HQ2 / sentiment" worked example, two different four-model panels. Either standardize on one four-model set throughout, or add one sentence on the judge slides explaining why the judge-distribution study uses a different roster than the criteria tables. As built, it reads like an error and quietly damages the reproducibility argument.

2. **Decide "five" vs "six" and make it deliberate.** Slide 3 says "Six decision points," slide 5 says "report all six decisions," slide 38 says "Document the six decisions." The paper is five decision points (Task, Model, Prompt, Evaluation, Reporting); Agents is your silent-a insertion. Recommend either (a) keep six but add a half-sentence on slide 3 or 9 like "the published framework has five steps; today we add Agents as a sixth," or (b) keep the framework at five and treat Agents as a bridge concept rather than a counted decision. Right now the count is asserted three times with no acknowledgement that it differs from the source.

3. **Fix the colons in rendered prose (house-style rule).** Three live violations:
   - Slide 1 kicker: `Beyond the Hype: Using Generative AI in Public Administration Research` (verbatim workshop title — if you want strict compliance, render it as "Beyond the Hype, Using Generative AI..." or drop the subtitle).
   - Slide 10 harness paragraph: "...A stateless model becomes an agent only through its harness. Claude Code is one**:** when the model says run the tests..." Change the colon to a period or comma: "Claude Code is one. When the model says run the tests, the harness runs them..."
   - Slide 14 button: "Access**:** chat vs API" → "Access, chat vs API" or "Chat vs API access."

4. **Fix the lowercase sentence-start typos on closing lines.** Slide 23 closing line reads "**validity** becomes accuracy, reliability becomes precision, error becomes uncertainty." It starts lowercase and reads as a typo at projector size. Capitalize: "Validity becomes accuracy, reliability becomes precision, error becomes uncertainty." (Confirm the same casing convention on every closing line — most are sentence-cased, so this one is the outlier.)

5. **Rework the PPI slide layout (slide 29).** The left-rail kicker labels collide with the body text: "GUARANTEE" runs straight into "The resulting confidence interval..." with no gap, and "ESTIMATOR" nearly touches "ML estimate...". Add column spacing or move the labels above their rows. This is the densest slide in the deck and the most numerically demanding for a non-technical audience; it currently looks crowded and slightly broken. Also consider whether PPI (which is your addition, not in the TaMPER paper) needs to be this detailed for a mixed audience — a single "same labels, 45 percent narrower interval" payoff with one small table may land better than three stacked tables.

6. **Thin slide 7 ("What is a task?").** It carries three cards (Input/output, Complexity, Model's function) plus a header note plus a four-column, three-row table. That is two slides of content. Recommend splitting the three-decision cards onto slide 7 and moving the participant/coder/extractor table to slide 8, or folding the table into the existing use-case switcher. As is, it is the highest cognitive-load non-interactive slide in the deck.

7. **Trim for time.** Candidates to cut or merge: slide 16 ("Tell it what you want") is two bullets and a one-liner and could merge into the Prompt divider or slide 17; slide 36 ("Report it back along the same five steps") substantially overlaps the interactive checklist on slide 37 and could be cut so the interactive one carries the section. That recovers 2 slides without touching the argument.

8. **Make the agentic-AI value land for a PA audience.** The Agents section is well-drawn but stays abstract (LLM A/B/C, tools, loops). For mixed-background PA scholars, one concrete research-relevant example of an agent ("an agent that pulls a city budget PDF, extracts line items, and cross-checks them against a database") would convert the diagrams into something they can picture using. Right now the section demonstrates *what an agent is* but not *why a PA researcher would reach for one*.

---

## 3. Slide-by-slide table (slides needing attention)

Slides not listed (2, 6, 9, 11, 13, 15, 18, 19, 20, 21, 24, 25, 26, 27, 30, 31, 32, 35, 37) were reviewed and are clean as-is.

| # | Title | Observation | Suggestion |
|---|-------|-------------|------------|
| 1 | TaMPERing Generative AI | Kicker subtitle contains a colon ("Beyond the Hype: Using..."). Layout and headshot are clean. | Render the workshop title without the colon for house-style compliance, or accept it as a verbatim quotation and note the exception. |
| 3 | TaMPER acronym, expanded | "Six decision points for using generative AI with rigor." Paper says five. | Acknowledge the five-vs-six difference once (see headline #2). |
| 4 | Researchers adopting faster than validating | Strong hook, but it is the only data point and sits in a lot of white space; the stat is real (Wiley 57%→84%) but unframed as to what "AI tool use" means. | Consider a one-line gloss ("self-reported use of any AI tool in the research process") so the jump is not over-read. Otherwise fine. |
| 5 | From gut feel to defensible | "report all six decisions." Same six-count issue. | Align with the chosen count. |
| 7 | What is a "task"? | Three cards + header note + 4-column/3-row table on one slide. Highest static density in the deck. | Split into two slides (see headline #6). |
| 8 | What scholars are doing with LLMs | Interactive switcher works well; default state reads clearly. The brain emoji in the LLM box is a touch informal next to the otherwise clean system. | Minor: consider a glyph/icon instead of the emoji for consistency. Otherwise keep. |
| 10 | Agentic workflow or agentic AI | Header is a 4-line paragraph wall; contains a colon ("Claude Code is one:"). Diagrams are good. | Tighten the paragraph to 2 lines and fix the colon (headline #3). The Claude Code aside is good but could move to speaker notes. |
| 12 | Good at complicated, shaky at unclear | The chart label "the gap widens" is rotated vertical and hard to read; the two-curve message is good but the dashed "judgment" curve is faint at distance. | Set "the gap widens" horizontal (or drop it), and thicken/darken the uncertainty curve. The "this is a synthesis, not a single measured law" caveat is good and honest — keep it. |
| 14 | Three decisions, click to explore | Button label "Access: chat vs API" has a colon. Content is solid. | "Chat vs API access" (headline #3). |
| 16 | Tell it what you want | Very sparse (2 bullets + italic line). The closing italic line sits tight under the second bullet rather than in the closing-line slot. | Merge into slide 17 or the Prompt divider to recover a slide; if kept, give the closing line its standard spacing. |
| 17 | Components, and order matters | The prompt template is small monospace and dense; at projector distance the highlighted section is legible but the body is borderline. | Increase the code font a step, or collapse the NEWS ARTICLE/DEFINITIONS block since it is illustrative. The interaction is good. |
| 23 | How do we know the output is good? | Closing line starts lowercase: "validity becomes accuracy...". Reads as a typo. | Capitalize "Validity" (headline #4). |
| 28 | Accuracy in action | The GPT OSS row shows McNemar 153.0 in gray italic with no stars while the takeaway calls it "noise." The visual coding (gray = noise) is not explained, and a large chi-square with no asterisk will confuse a stats-literate viewer who expects significance to mean a real difference. | Add a one-line legend for the gray styling ("gray = no meaningful accuracy gain") or briefly say in the takeaway why a significant chi-square here is treated as noise (the revised prompt did not improve accuracy for GPT OSS). Right now the styling carries meaning the slide never defines. |
| 29 | Scaling honestly with PPI | Left-rail labels (SETUP / ESTIMATOR / GUARANTEE) collide with body text; "GUARANTEE" abuts "The resulting" with no gap. Three stacked tables. PPI is not in the TaMPER paper. | Fix spacing (headline #5); consider simplifying for the audience and flagging PPI as an extension beyond the paper. |
| 33 | Harsh vs not-harsh distributions | Uses Command A, **Gemma 3**, GPT OSS, Phi 4 — different roster than the criteria tables (which use Qwen 3, not Gemma 3). | Standardize the model set or explain the difference (headline #1). |
| 34 | Judge scores track accuracy | Same Gemma-3 roster mismatch; also the per-panel n breakdown text is small and tight under each chart. | Same fix as 33; consider moving the n counts to a single shared caption. |
| 36 | Report it back along the same five steps | Largely duplicates the interactive checklist on slide 37 (Task/Model/Prompt/Evaluation). Note it correctly says "five steps" here, which contradicts the "six decisions" on slides 3/5/38. | Cut this slide and let the interactive 37 carry Reporting, or reconcile the five/six wording. |
| 38 | Three things to take into your next study | "Document the six decisions" — six again. Good, memorable close otherwise. | Align the count; everything else here is strong. |

---

## 4. Quick wins (small fixes)

- **Colon fixes** (3): slide 1 title subtitle, slide 10 "Claude Code is one:", slide 14 "Access:" button.
- **Capitalize** slide 23 closing line "validity → Validity."
- **Five vs six** wording appears on slides 3, 5, 36 (says five), 38. Make them all agree.
- **PPI slide label spacing** (slide 29) — pure CSS gap fix, highest-visibility cosmetic bug.
- **Slide 12** chart: set "the gap widens" label horizontal; darken the dashed uncertainty curve.
- **Slide 8** LLM-box emoji → consider a consistent icon.
- **Slide 17 / 28 / 34** have the smallest type in the deck (monospace prompt, gray McNemar note, per-panel n counts). Bump one step for projector legibility.
- **Citation format consistency**: most cites are "(Author Year)" linked; the PPI cite on slide 29 is "(Angelopoulos et al. 2023, Science)" with the venue appended, which is the only one that names a journal. Either add venues everywhere or drop it here for consistency.
- **Confirm the McNemar gray-styling legend** is defined on slide 28 (currently the gray = "noise" convention is implicit).

---

## Accuracy spot-check notes (against `tamper_paper_extracted.md`)

- **Framework decision points**: paper = five (Task, Model, Prompt, Evaluation, Reporting). Deck = six (adds Agents). Deck's addition is legitimate but uncounted-difference is never flagged. **Flag.**
- **Task definition** ("set of actions that transform input data into the desired output"): matches the paper (line ~438). **OK.**
- **Participant / Coder / Human extractor table** (slide 7): matches the paper's task table (Participant→Synthetic Data Generation, Coder→Text Analysis, Human extractor→Text Analysis). **OK.**
- **Compliance / Accuracy / Precision / Quality** floor: paper treats these as the evaluation criteria with quality as higher-order; the deck's stronger "logically dependent, establish each before the next" framing (slide 26) is a reasonable pedagogical synthesis but is more rigid than the paper states. **OK as teaching device; not a misquote.**
- **Role specification** recommendation (slide 17: "Do not use role specification, unless you are building a silicon sample"): paper says use it "sparingly," benefits smaller models, negligible on larger ones (Kim et al. 2023; Argyle et al. 2023). Deck states it more absolutely than the paper. **Minor — consider softening to "use sparingly."**
- **Structured output → ~100% compliance** (slides 20, 27): consistent with the paper's True Structured Output discussion and the deck's own compliance table. **OK.**
- **PPI / Angelopoulos et al. 2023** (slide 29): not in the TaMPER paper; this is the deck's own methodological extension. Accurate to the PPI literature as far as the numbers shown, but it is beyond the source. **Flag as an extension, not a contradiction.**
- **944 tweets, Stokan et al. 2025, Amazon HQ2** (slide 37 reported example): external study used as the worked case; not verifiable against the TaMPER paper here. Make sure this citation is correct in your own records.
- **Wiley 57%→84%** (slide 4): external stat, plausible and linked; verify the Wiley source still supports both figures before presenting.
