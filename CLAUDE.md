# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Quarto presentation ("Developing Good Research Habits") by Rob J Hyndman, delivered as a Beamer PDF slide deck using the `quarto-monash/presentation` extension. The single source file is `ResearchHabits.qmd`.

## Build Command

```bash
quarto render ResearchHabits.qmd
```

This produces `ResearchHabits.pdf` via pdflatex. The presentation uses the `presentation-beamer` format defined in `_extensions/quarto-monash/presentation/`.

## Structure

- `ResearchHabits.qmd` — the entire presentation source (Quarto markdown with embedded R chunks and raw LaTeX)
- `preamble.tex` — LaTeX preamble included in the beamer output
- `figs/` — images referenced in slides
- `_extensions/quarto-monash/presentation/` — the Monash University Quarto extension providing the beamer theme (`beamerthemeMonash.sty`), title/TOC partials, and background images

## Key Details

- The extension supports `presentation-beamer`, `presentation-revealjs`, and `presentation-revealjs+letterbox` formats; this repo only uses beamer.
- Slides mix Quarto markdown with raw LaTeX commands (`\placefig`, `\begin{textblock}`, `\only<n->`, etc.) for precise layout control.
- R code chunks (knitr) are used with `cache = TRUE`; the `.quarto/` cache directory is gitignored.
- The `titlegraphic` and `titlecolor` YAML keys are Monash-extension-specific options.
