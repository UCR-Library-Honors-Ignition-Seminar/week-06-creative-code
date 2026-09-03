# Week 6 Slides — Creative Code & Games

Quarto `revealjs` decks for two 90-minute honors seminar sessions.
Source template: `github.com/UCR-Library-Honors-Ignition-Seminar/week-06-creative-code`

## Files

| File | Session |
|---|---|
| `session-1-p5js.qmd` | 1 — Generative Visuals with p5.js |
| `session-2-bitsy.qmd` | 2 — Space as Narrative with Bitsy |
| `_quarto.yml` | shared format + author block |
| `assets/slides.scss` | UCR-brand theme (blue `#003da5` / gold `#ffb81c`) |
| `logo.png` | UC Riverside Library logo |

## Build / preview

```bash
quarto preview session-1-p5js.qmd    # live-reload
quarto render                        # both → _output/
```

`. . .` = fragment break · `#` slides = blue section dividers · gold slides = hands-on exercises.
Present: `S` speaker view · `O` overview · `F` fullscreen · `B` chalkboard.

## Adding to the course repo

Same three options as `week-05-slides/README.md`: a `slides/` subfolder in the
week repo, GitHub Pages via `quarto-actions`, or keep separate and hand out PDF exports.
