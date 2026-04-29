# COMP/STAT 212 Portfolio — Spring 2026

This repo is the **Quarto book portfolio** of **Zhijun He (何智骏)**, Macalester '26, for *COMP/STAT 212: Intermediate Data Science* with Prof. Brianna Heggeseth ("Hash") at Macalester College, Spring 2026.

It collects the non-homework work of the semester: weekly TidyTuesday submissions, in-class activities, pre-class learning syntheses, professor-viz recreations, and side analyses.

> The graded homework lives in a separate repository: [`mac-stat212-s26/homework-Zhijun1933`](https://github.com/mac-stat212-s26/homework-Zhijun1933).

## Reading the rendered book

The book is configured in `_quarto.yml` and renders to `docs/`. Themes are `flatly` (light) and `darkly` (dark); code blocks are foldable, and the sidebar is docked.

To build locally:

```bash
quarto render
```

`freeze: auto` is on, so unchanged chapters skip re-execution on rebuild — important because some TidyTuesday chapters fetch data from `tidytuesdayR` or live URLs.

## Sections

The book has five chapter groups, each with its own README that introduces the work in that group:

| Section | Path | What's in it |
|---------|------|--------------|
| **Prof Viz** | [`pv/`](pv/pv-README.qmd) | Recreations of visualizations Hash showed in lecture |
| **TidyTuesday** | [`tt/`](tt/tt-README.qmd) | 13 weekly TidyTuesday submissions (weeks 4–16) — solo and collaborative — including a multi-author analysis of capital concentration in Brazil's CNPJ business registry |
| **Pre-Class Learnings** | [`pcl/`](pcl/pcl-README.md) | Three exam-prep syntheses summarizing the major course units, with hand-drawn diagrams scanned in as PNG |
| **In-Class Activities** | [`ica/`](ica/ica-README.qmd) | ICAs 01–19: data viz, advanced maps, wrangling I/II, missing data, functions, base R, loops/iteration, APIs I/II, web scraping, SQL, effective viz, interactive viz, quality control |
| **Extras** | [`extra/`](extra/extra-README.qmd) | Side analyses outside the assigned scope — `mice` imputation demo, pagination simulation, deeper-cut version of the CNPJ capital analysis |

## Repository structure

```
portfolio-Zhijun1933-212/
├── _quarto.yml          # book config (chapter order, theme, sidebar)
├── index.qmd            # Welcome page
├── 404.qmd              # Custom 404 page
├── README.md            # this file
├── portfolio.Rproj      # RStudio project root
├── _freeze/             # Quarto's per-chapter execution cache
├── docs/                # rendered output (deployed site)
├── assets/              # sidebar logo, 404 image, shared assets
├── style/               # custom.css for typography overrides
├── pv/                  # Prof Viz chapters
├── tt/                  # TidyTuesday chapters
├── pcl/                 # Pre-class learning chapters + exam diagrams
├── ica/                 # In-class activity chapters + ica/data/
├── extra/               # Side analyses
└── src/                 # Working space for ICA 04 (advanced maps)
                        # — code/, data/, figures/ split, not rendered
                        #   into the book directly
```

## Notes on the build

- HTML output uses `embed-resources: true`; each rendered chapter is portable
- Code is folded by default (`code-fold: true`) — readers see prose first, expand on demand
- Custom typography in `style/custom.css`
- Theme follows the reader's system preference

`.bak` files in `tt/` and `ica/` are backups from in-progress edits; the `_quarto.yml` chapters list is the canonical chapter set.

## Tooling

R 4.x with the tidyverse, plus chapter-specific packages — `sf` and `tidycensus` for spatial work, `gt` for tables, `rvest` for scraping, `mice` for imputation, plus the usual ggplot2 extension stack (`patchwork`, `scales`, `ggtext`).

---

*Spring 2026 · Macalester College*
