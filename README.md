# IEAP Series 02 — RStudio: Statistical Tests

**Université de Montpellier | Master IEAP | 2026–2027**  
**Course assignment:** Series 02 — Data Mining and Statistical Tests

**Team members:** Jennifer Houmard, Jeanne Le Roux, and Jiangbin Long

## Project overview

This repository contains a collaborative statistical analysis project completed in **RStudio** using **R**, **Quarto**, and **Git/GitHub**. The aim is to explore datasets, select appropriate statistical methods, interpret results, and produce a reproducible report. It also documents how the group organized its work through branches, commits, pull requests, and code reviews.

The analyses focus on statistical concepts, the effect of rehabilitation treatment over time, and relationships between snoring, body mass index (BMI), alcohol consumption, smoking status, sex, height, and weight.

**[Read the final report (PDF)](IEAP-Series02-Rstudio.pdf)** · **[View the master Quarto notebook](IEAP-Series02-Rstudio.qmd)**

## Research questions and methods

| Topic | Main question or task | Analysis |
| --- | --- | --- |
| Statistical foundations | How should statistical tests be selected and interpreted? | Descriptive statistics, distributions, assumptions, p-values, paired/unpaired data |
| Rehabilitation | Does measured performance change after treatment? | Paired observations, Shapiro–Wilk normality test, paired *t*-test, paired line plot |
| Snoring and BMI | Do snorers have a higher BMI? | Group descriptives, boxplots, Shapiro–Wilk test, Wilcoxon rank-sum test |
| Snoring and alcohol | Do snorers consume more alcohol? | Group comparison and Wilcoxon rank-sum test |
| Snoring and smoking | Is smoking status associated with snoring? | Proportions and chi-square test of independence |
| Sex and BMI | Is BMI different between men and women? | Group comparison and Wilcoxon rank-sum test |
| Sex and smoking | Is smoking status associated with sex? | Proportions and chi-square test of independence |
| Numerical relationships | Which numerical variables are correlated? | Spearman correlation matrix and significance testing |

The report includes the R code, tables, plots, statistical outputs, interpretations, references, and a grading checklist. Its conclusions are specific to the datasets analysed and should not be treated as causal findings.

## Repository structure

```
IEAP-Series02-RStudio/
├── README.md
├── LICENSE
├── .gitignore
├── _quarto.yml
├── IEAP-Series02-RStudio.Rproj
├── IEAP-Series02-Rstudio.qmd
├── IEAP-Series02-Rstudio.pdf
├── data/
└── sections/
    ├── 01_git_workflow.qmd
    ├── 02_statistical_test_concepts.qmd
    ├── 03_treatment_over_time.qmd
    ├── 04_snorers_fatter.qmd
    ├── 05_snorers_drink_smoke.qmd
    ├── 06_men_fatter.qmd
    ├── 07_women_smoke_less.qmd
    ├── 08_variable_correlations.qmd
    ├── 09_challenges_lessons.qmd
    ├── 10_sources_references.qmd
    ├── 11_checklist.qmd
    └── 12_final_report_fixes.qmd
```

The **master `.qmd` file** assembles the report using Quarto `include` directives. Each topic is stored in a separate section file so team members can develop and review their work without editing the same document simultaneously. The master document controls the report title, authors, table of contents, numbering, and PDF formatting.

## How to reproduce the report

**Requirements:** [R](https://www.r-project.org/), [RStudio](https://posit.co/download/rstudio-desktop/), and [Quarto](https://quarto.org/docs/get-started/). Quarto uses the **Typst** format to produce the PDF.

1. Clone the repository:

   ```
   git clone https://github.com/jenniferhoumard/IEAP-Series02-RStudio.git
   cd IEAP-Series02-RStudio
   ```

2. Open `IEAP-Series02-RStudio.Rproj` in RStudio.
3. Install the main R package dependency if needed:

   ```r
   install.packages("tidyverse")
   ```

4. Open `IEAP-Series02-Rstudio.qmd` and click **Render** in RStudio. Alternatively, from the repository root:

   ```
   quarto render IEAP-Series02-Rstudio.qmd --to typst
   ```

The master document loads `tidyverse` in its setup chunk. The `_quarto.yml` configuration sets the execution directory to the project root, so data are accessed with relative paths such as `data/PrePost copy.csv` and `data/snore copy.csv`. Keep the existing `data/` and `sections/` folders in place when rendering.

## Collaboration and Git workflow

The repository was organized for parallel team development:

1. The initial project structure and section templates were created on `main`.
2. Each section was developed on its **own branch**, with meaningful commits documenting progress.
3. Completed sections were published to GitHub and submitted as **pull requests**.
4. Team members reviewed code, answers, and formatting before merging changes into `main`.
5. The group carried out a final integration pass to standardize wording, citations, package loading, data paths, and report formatting.

The `main` branch was protected against accidental deletion and required pull requests, at least **one approval**, and resolution of review conversations before merging. A detailed explanation of the branch strategy and lessons learned is included in the report.

## Challenges and lessons learned

The group encountered several practical issues during collaborative development, including sharing datasets after branches had already been created, keeping local copies synchronized using **Fetch origin**, managing repeated R library imports, and ensuring all included Quarto sections worked together from a clean session. These experiences informed the final project setup and review process.

## Data, sources, and references

The datasets used in the assignment were supplied by the course instructor. Supporting statistical literature, references, and source information are documented in the report's **Sources and References** section. The `data/` folder contains the files needed to reproduce the relevant analyses.

## License

See [LICENSE](LICENSE) for the repository's license terms. Dataset and third-party material rights may be separate from the repository's code license.
