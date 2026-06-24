# Git & GitHub team demo

A hands-on, ~60–90 minute demo that walks an entire team through the emLab Git
workflow on a **shared practice repo**: protecting `main`, cloning, formatting
with Air, branching, pull requests, code review, issues, and merge conflicts.

The slide deck (`index.qmd`) is the script — every live-coding step has a slide,
and each action slide marks **who acts** ([WATCH]/[EVERYONE]) and **where**
(github.com / Positron / RStudio / Terminal).

## Files

- `index.qmd` — the revealjs slide deck.
- `emlab-demo.scss` — emLab-styled theme (emLab blue, role/tool badges).
- `images/emlab_logo_horizontal.svg` — logo used on the title slide and footer.
- `images/git_commit_2x.png` — xkcd #1296 (CC BY-NC), used on the commit slide.
- `README.md` — this presenter guide.

## Render / present the deck

```bash
quarto preview demo/index.qmd   # live preview while editing
quarto render  demo/index.qmd   # build demo/index.html
```

Present from the rendered HTML in a browser. Useful reveal.js keys: `S` =
speaker notes (each slide has presenter notes), `F` = fullscreen, `O` = slide
overview, `Esc` = exit.

## Before the session (presenter checklist)

1. **Create a throwaway shared repo** in the `emlab-ucsb` org, e.g.
   `git-demo-2026`. Add every participant as a collaborator with **Write**
   access (Settings → Collaborators and teams).
2. **Seed the starter content** (see below) and commit it to `main` *before*
   you turn on the ruleset.
3. **Do not** create the ruleset yet — you protect `main` live in Section 1 so
   people see it happen.
4. Confirm everyone can (a) see the repo on github.com and (b) authenticate to
   GitHub (PAT or SSH). Have the SOP "Getting set up" page handy for stragglers.
5. Pair people up ahead of time: **A reviews B, B reviews A.** The code-review
   sections depend on each person having a reviewer.

## Starter repo content

A minimal structure that makes every section work — especially the
**deterministic merge conflict**, which needs a single shared line everyone
edits:

```
git-demo-2026/
├── README.md
├── R/
│   ├── pair-1.R        # <- one conflict file per PAIR
│   ├── pair-2.R
│   └── pair-3.R        # add as many as you have pairs
└── team/
    └── .gitkeep        # everyone adds team/<name>.R here
```

Each `R/pair-N.R` holds the one shared line that pair's conflict is built on:

```r
# Conflict practice file for pair N
project_version <- "0.1.0"
```

`README.md` — anything short; a title and a one-line description is enough.

`team/.gitkeep` — empty file so the folder exists. In Section 5 each participant
adds their own `team/<name>.R`, so individual changes never collide.

## How the merge conflict is engineered (Section 7)

A conflict requires **two people editing the same line**. To avoid the whole room
fighting over one file, **each pair gets its own file** (`R/pair-N.R`). Pre-seed
one file per pair and tell each pair which is theirs.

Within a pair (Partner A and Partner B both branch from `main`):

1. **Partner A** sets `project_version` to `"0.2.0"`, opens a PR, and **merges it
   to `main` first**.
2. **Partner B** sets the same line to a different value (`"0.9.0"`) on their
   branch, pushes, and opens a PR. GitHub reports the PR can't auto-merge.
3. **Partner B** resolves it **on github.com** (Resolve conflicts → keep one line
   → Mark as resolved → Commit merge), or locally via the Positron/VS Code merge
   editor. The deck de-emphasizes the terminal here on purpose.
4. Swap roles so each person resolves a conflict once.

Partner A must merge before Partner B opens their PR, or the conflict won't
appear. If you don't know pairs in advance, have each pair create their own file
together at the start of the section instead of pre-seeding.

> Note: a plain "Pull"/"Sync" only updates the current branch from its own
> remote — it does **not** pull `main` into a feature branch. The deck has a slide
> making this explicit; the simplest path is to let the PR surface the conflict on
> github.com.

> On auto-closing issues: per GitHub's docs, the reliable trigger is a closing
> keyword (`Closes #N`) in the PR description — **creating a branch from an issue
> links them but does not by itself close the issue on merge.** The deck reflects
> this (Section 6 / Example 1).

## Timing guide (rough)

| Section | Topic | Who | ~min |
|---|---|---|---|
| 1 | Protect `main` (ruleset) | Watch | 8 |
| 2 | Clone the repo | Everyone | 8 |
| 3 | Air formatter setup | Everyone | 6 |
| 4 | Create an issue → branch from it | Everyone | 10 |
| 5 | Change → commit → push | Everyone | 12 |
| 6 | Open PR + assign reviewer | Everyone | 8 |
| 7 | Example 1: request changes → merge (closes issue) | Everyone | 12 |
| 8 | Example 2: new branch → reviewer edits → merge | Everyone | 10 |
| 9 | Merge conflict | Everyone | 12 |

## Source

Built from the emLab Standard Operating Procedures
(<https://emlab-ucsb.github.io/SOP/>) — Getting set up, Branches, Pull Requests,
Issues, Rulesets, Code Review, and Code Styling. Keep the deck in sync with
those pages if the SOP changes.
