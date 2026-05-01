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
install.packages(c("tidyverse", "lubridate", "nycflights13", "bookdown", "fpp3"))
```

`fpp3` (Forecasting: Principles and Practice) bundles `tsibble`, `tsibbledata`, `feasts`, `fable`, and related packages used from Lab03 onward.

## Lab Topics

| Directory | Tutorial week | Key packages | Topic |
|-----------|--------------|--------------|-------|
| Lab01 | Week 1 | tidyverse | `dplyr` / `ggplot2` — NBA player data |
| Lab02 | Week 2 | lubridate, tidyverse | Date/time manipulation; `nycflights13` |
| Lab03 | Week 3 | fpp3 | Time series exploration (`aus_retail`) |
| Lab04 | Week 4 | fpp3 | Moving averages and decomposition |
| Lab05 | Week 7 | fpp3, gridExtra | Exponential smoothing (ETS models) |

Note: Lab05 contains the Week 7 tutorial — the directory numbering and week numbering diverge from Lab05 onward.

## Structure

Each `LabNN/` directory follows the same pattern:
- `tutorial_week_NN.Rmd` — student-facing exercises (incomplete code chunks)
- `tutorial_week_NN_solutions.Rmd` — complete worked solutions
- `*.html` — pre-rendered outputs
- Data files (e.g., `basketball.csv`) and additional stand-alone Rmds (e.g., `model_answer.Rmd`, `q3*.Rmd`) where present

## Conventions

- Chunk option `cache = TRUE` is used throughout — delete `*_cache/` directories if stale cache causes issues.
- Exercises use `bookdown` cross-references (`\@ref()`), so render with `rmarkdown::render()` (not plain `knitr::knit()`).
- Student exercise chunks are left intentionally empty; solutions are in `*_solutions.Rmd`.
- The YAML front matter is identical across all labs — copy it verbatim when creating a new tutorial.
