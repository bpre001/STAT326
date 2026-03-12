# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Course materials for STAT326/786 (Statistics) at the University of Auckland. Labs are organized by week, each containing an incomplete tutorial `.Rmd`, a solutions `.Rmd`, and rendered `.html` outputs.

## Rendering R Markdown

To render an `.Rmd` file to HTML, run in R:

```r
rmarkdown::render("Lab01/tutorial_week_01.Rmd")
```

Or use the **Knit** button in RStudio. Output format is `bookdown::html_document2` with a floating TOC and code folding.

## Key Dependencies

```r
install.packages(c("tidyverse", "lubridate", "nycflights13", "bookdown"))
```

## Structure

Each `LabNN/` directory follows the same pattern:
- `tutorial_week_NN.Rmd` — student-facing exercises (incomplete code chunks)
- `tutorial_week_NN_solutions.Rmd` — complete worked solutions
- `*.html` — pre-rendered outputs
- Data files (e.g., `basketball.csv`) where needed

## Conventions

- Chunk option `cache = TRUE` is used throughout — delete `*_cache/` directories if stale cache causes issues.
- Exercises use `bookdown` cross-references (`\@ref()`), so render with `bookdown::render_book()` or `rmarkdown::render()` (not plain `knitr::knit()`).
