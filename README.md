# BIOS 640 – Week 4: Reproducible reporting with R Markdown and GitHub

This repository contains my Week 4 assignment for BIOS 640 (Introduction to Health Data Science Methods, McGill University). It builds on my Week 3 NHANES analysis and turns it into shareable outputs: a customised HTML report, a dashboard, and a PDF report with formatted tables.

## Repository structure

| Folder / file | Contents |
|---|---|
| `data/` | `cleaned_NHANES.csv` (cleaned NHANES extract) and `diet.csv` (weight data used in the Week 3 report) |
| `code/` | R Markdown sources: `week3_report.Rmd` (HTML report), `week4_dashboard.Rmd` (flexdashboard), `week4_tables_report.Rmd` (PDF report with tables) and `references.bib` (bibliography) |
| `figures/` | Plots saved by the Week 3 report (e.g. `age_distribution.png`, used in the dashboard) |
| `reports/` | Rendered outputs: `week3_report.html`, `week4_dashboard.html` and `week4_tables_report.pdf` |
| `.here` | Marks the project root so that `here()` file paths work on any computer |

## Exercises and where to find them

- **Exercise 1:** this repository (structure, README and commit history).
- **Exercise 2:** `code/week3_report.Rmd` and `reports/week3_report.html`. The original version (PDF output) was committed to `main` first. The changes (HTML output, theme, floating table of contents, tabbed figures and interactive DT table) were made on the branch `customize-html-output`, which was merged into `main` and then deleted.
- **Exercise 3:** `code/week4_dashboard.Rmd` and `reports/week4_dashboard.html`.
- **Exercise 4:** `code/week4_tables_report.Rmd` and `reports/week4_tables_report.pdf`.

## How to reproduce

1. Clone the repository and open the folder in RStudio.
2. Install the packages: `rio`, `here`, `tidyverse`, `cowplot`, `ggpubr`, `DT`, `flexdashboard`, `knitr` and `kableExtra`. The PDF report also needs LaTeX (e.g. `tinytex::install_tinytex()`).
3. Knit the files in this order, because the Week 3 report saves the figures used by the dashboard:
   1. `code/week3_report.Rmd`
   2. `code/week4_dashboard.Rmd`
   3. `code/week4_tables_report.Rmd`

All file paths use `here()`, and the rendered files are already included in `reports/`, so nothing needs to be rendered to view them.

## Data source

Centers for Disease Control and Prevention (CDC), National Center for Health Statistics (NCHS). *National Health and Nutrition Examination Survey (NHANES)*. https://www.cdc.gov/nchs/nhanes/

Note: the NHANES variables `gender` and `ethnicity` use older labels and actually capture biological sex and race. The original labels are kept in the data, as required by the assignment.
