# math-stats-1

Public-facing Quarto course site for **Mathematical Statistics I** (MATH 75063), a graduate
course in the mathematical-statistics sequence at UA Little Rock. Sibling to the
main site [matthewhester.com](https://matthewhester.com); lives at `/math-stats-1/`
under that domain.

## Status: public materials in development

The **course** is an established graduate catalog course. The **public
materials** in this repo are in development: dates, policies, assessments, and
readings are provisional, and the term shown on the site is a planning
assumption rather than a scheduled section. That is stated on the landing page,
in the syllabus summary, and in the site footer, and it is what the course
registry record on the hub says too. Do not relabel this site as a current
offering until the term, section, meetings, and release decisions are actually
settled.

Blackboard remains the official operational course home. Grades, due dates,
submissions, announcements, and section-specific material live there; this
public site does not duplicate it.

## What is here

- `index.qmd` — landing page, outcomes, how the course runs
- `syllabus.qmd` — public syllabus summary (not the operational syllabus)
- `schedule.qmd` — unit schedule
- `notes/` — 16 unit pages, Week 0 through Week 15
- `resources/` — supporting resource collection
- `assets/figures/` — 64 static SVG figures, pre-rendered, never chunk-executed
- `styles/course_family_sections.css` — course-family presentation and the
  overflow-containment rules for MathML, wide tables, and figures

Sidebar entries carry the unit ordinal and subject ("1 — Readiness and the
probability bridge"), matching the rest of the course family. The ordinal runs
one ahead of the week number because the readiness unit is Week 0.

## Provenance and the private workspace

These pages were produced in a private authoring workspace on Drive
(`Teaching/courses/math-stats-1/course-draft`) through the Course Draft kernel, under a recorded
approval and a run receipt, and were independently reviewed there before
promotion. Only the public surface is copied here. The kernel's build state
(`_state/`), approval packets, resolved plans, asset bundles, and review notes
are not part of this repository and are `.gitignore`'d as a backstop.

Substantive content changes belong in that private workspace and are promoted
here, not edited in place — otherwise this repo drifts from the run receipt.
Two edits were made at promotion time and are not in the upstream draft: the
"Materials in development" callout on `index.qmd` and the expanded Logistics
paragraph in `syllabus.qmd`, both required for the In-development status by
`TEACHING_PORTFOLIO_ARCHITECTURE.md` on the hub.

## Deployment

This repo does **not** self-deploy and has no CI of its own. The hub repo
`matthewahester/matthewhester-site` checks it out in
`.github/workflows/publish.yml`, runs `quarto render`, and copies `_site/` into
`_site/math-stats-1/` of the combined GitHub Pages artifact. Publishing is a manual
`workflow_dispatch` on that repo.

Mathematics renders as browser-native MathML (`html-math-method: mathml`); no
MathJax runtime is loaded. Code is shown as teaching material and is never
executed at render time (`execute.enabled: false`), so no R or Python runtime is
needed to build this site.

## Local development

```bash
quarto render     # writes _site/ (gitignored)
quarto preview    # local preview with live reload
```
