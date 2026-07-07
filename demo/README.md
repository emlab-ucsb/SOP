# Git & GitHub team demo

A hands-on, ~60–90 minute demo that walks an entire team through the emLab Git
workflow on a **shared practice repo**: protecting `main`, cloning, formatting
with Air, branching, pull requests, code review, issues, and merge conflicts.

The slide deck (`index.qmd`) is the script — every live-coding step has a slide,
and each action slide marks **who acts** ([WATCH]/[EVERYONE]) and **where**
(github.com / Positron / VS Code / RStudio / Terminal).

## Links

- **SOP refresh slides:** <https://emlab-ucsb.github.io/SOP/slides/sop-overview>
- **Demo slides:** <https://emlab-ucsb.github.io/SOP/demo/>
- **Demo repo (we work off of this):** <https://github.com/emlab-ucsb/sop-demo>

## Files

- `index.qmd` — the revealjs slide deck.
- `emlab-demo.scss` — emLab-styled theme (emLab blue, role/tool badges).
- `images/` — logo and images used throughout the deck.
- `README.md` — this guide.

## Render / present the deck

```bash
quarto preview demo/index.qmd   # live preview while editing
quarto render  demo/index.qmd   # build demo/index.html
```

Present from the rendered HTML in a browser. Useful reveal.js keys: `S` =
speaker notes (each slide has presenter notes), `F` = fullscreen, `O` = slide
overview, `Esc` = exit.

## Source

Built from the emLab Standard Operating Procedures
(<https://emlab-ucsb.github.io/SOP/>) — Getting set up, Branches, Pull Requests,
Issues, Rulesets, Code Review, and Code Styling. Keep the deck in sync with
those pages if the SOP changes.
