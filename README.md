# IEAP Series 02 — RStudio: Statistical Tests

**Université de Montpellier | Master IEAP | 2026–2027**  
**Course assignment:** Series 02 — Data Mining and Statistical Tests

**Team members:** Jennifer Houmard, Jeanne Le Roux, and Jiangbin Long

## Project overview

The objectives of this assignment were to:

- Explore and visualize datasets using R.
- Select appropriate statistical tests based on the data and their assumptions.
- Interpret statistical results and answer research questions.
- Develop a reproducible Quarto report.
- Practice collaborative development using Git branches, commits, pull requests, and code reviews.

The project examines the effects of rehabilitation treatment over time and relationships between snoring, BMI, alcohol consumption, smoking status, sex, height, and weight.

**[Final Report (PDF)](IEAP-Series02-Rstudio.pdf)** | **[Master Quarto Document](IEAP-Series02-Rstudio.qmd)**

## Statistical Analyses

The assignment covers descriptive statistics, statistical hypothesis testing, parametric and non-parametric comparisons, and correlation analysis.

| Research Question | Statistical Method | Main Finding |
|---|---|---|
| Does performance change after rehabilitation? | Shapiro–Wilk, paired t-test | Significant increase in measured performance (p = 0.001) |
| Are snorers fatter? | Wilcoxon rank-sum | No significant BMI difference (p = 0.951) |
| Do snorers drink more? | Wilcoxon rank-sum | Higher alcohol consumption among snorers (p = 0.009) |
| Do snorers smoke more? | Chi-square | No significant association (p = 0.407) |
| Are men fatter? | Wilcoxon rank-sum | No significant BMI difference (p = 0.488) |
| Do women smoke less? | Chi-square | Lower smoking proportion among women (p = 0.008) |
| Are numerical variables correlated? | Spearman correlation | Strong positive height–weight correlation (ρ = 0.930, p < 0.001) |

The analyses were conducted using the provided datasets. Results indicate associations or differences within these samples, without establishing causality.

The complete statistical output, plots, interpretations, and assumptions are documented in the final report.

## Repository Structure

The repository uses **one master Quarto document** and **11 separate section documents**.

```
IEAP-Series02-RStudio/
├── README.md
├── LICENSE
├── .gitignore
├── _quarto.yml
├── IEAP-Series02-RStudio.Rproj
├── IEAP-Series02-Rstudio.qmd
├── IEAP-Series02-Rstudio.pdf
│
├── data/
│   ├── PrePost copy.csv
│   └── snore copy.csv
│
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
    └── 11_checklist.qmd
```

The master `.qmd` document assembles the individual sections using Quarto `include` directives. This structure allowed team members to work on separate files simultaneously, reducing the risk of merge conflicts.

The master document also manages the report's title, authors, table of contents, section numbering, and PDF formatting.

## Collaboration and Git Workflow

The project was developed using **13 Git branches**: 11 for individual report sections and 2 for final integration and corrections.

The collaborative workflow followed these steps:

1. **Initial setup:** The shared GitHub repository, master document, and section templates were created on `main` by one student.
2. **Parallel development:** Each team member worked on their assigned sections in separate branches.
3. **Version control:** Progress was documented through meaningful commits.
4. **Pull requests:** Completed sections were submitted as pull requests into `main`.
5. **Team review:** All three team members reviewed the sections, code, and results before merging.
6. **Final integration:** Additional branches were used to improve consistency and produce the final report.

### Branches and Task Distribution

| Branch | Team Member | Purpose |
|---|---|---|
| `01_git_workflow` | Jennifer Houmard | Git workflow and collaboration |
| `02_statistical_test_concepts` | Jiangbin Long | Statistical concepts |
| `03_treatment_over_time` | Jeanne Le Roux | Rehabilitation treatment analysis |
| `04_snorers_fatter` | Jennifer Houmard | Snoring and BMI |
| `05_snorers_drink_smoke` | Jiangbin Long | Snoring, alcohol, and smoking |
| `06_men_fatter` | Jeanne Le Roux | BMI comparison by sex |
| `07_women_smoke_less` | Jennifer Houmard | Smoking comparison by sex |
| `08_variable_correlations` | Jiangbin Long | Correlation analysis |
| `09_challenges_lessons` | Jeanne Le Roux | Challenges and lessons learned |
| `10_sources_references` | Jiangbin Long | Sources and references |
| `11_checklist` | Jeanne Le Roux | Final grading checklist |
| `12_final_report_fixes` | Jennifer Houmard | Report integration and corrections |
| `13_other_final_fixes` | Jeanne Le Roux | Additional final corrections |

### Branch Protection and Reviews

The `main` branch was protected using GitHub repository rules to prevent accidental deletion or unauthorized changes.

Merging required:

- A pull request.
- At least one approval.
- Resolution of review conversations.

These rules ensured that changes were reviewed before they were incorporated into the final report.

## Reproducing the Report

### Requirements

- [R](https://www.r-project.org/)
- [RStudio](https://posit.co/download/rstudio-desktop/)
- [Quarto](https://quarto.org/docs/get-started/)
- R package: `tidyverse`

The PDF report is generated using Quarto's **Typst** output format.

### Instructions

**1. Clone the repository**

```bash
git clone https://github.com/jenniferhoumard/IEAP-Series02-RStudio.git
cd IEAP-Series02-RStudio
```

**2. Open the RStudio project**

Open `IEAP-Series02-RStudio.Rproj` in RStudio.

**3. Install the required R package if necessary**

```r
install.packages("tidyverse")
```

**4. Render the report**

Open `IEAP-Series02-Rstudio.qmd` in RStudio and click **Render**.

Alternatively, from the project root:

```bash
quarto render IEAP-Series02-Rstudio.qmd --to typst
```

The project uses `_quarto.yml` to set the working directory to the repository root. This ensures that relative paths such as `data/PrePost copy.csv` work consistently across the report.

## Challenges and Lessons Learned

Collaborative development required several adjustments:

- **Git workflow:** Adapting from individual file management to parallel work using branches and pull requests.
- **Shared datasets:** Adding the data folder after development had begun and synchronizing changes using GitHub Desktop.
- **R dependencies:** Moving repeated library imports into the master Quarto setup.
- **Report integration:** Correcting file paths, formatting, and citations to ensure consistent rendering.

These challenges helped the team improve its understanding of reproducibility, version control, and collaborative project organization.

A more detailed reflection is included in the final report.

## Sources and References

Statistical references and supporting literature are documented in the **Data Sources** and **Scientific References** sections of the final report.

The `data/` folder contains the datasets required to reproduce the statistical analyses.

## License

See [LICENSE](LICENSE) for the repository's license terms. Third-party sources and datasets may be subject to separate usage rights.
