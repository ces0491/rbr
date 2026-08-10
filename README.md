# Ready Before Run()

A Practical Guide to Gear Up for Data Science, by [Cesaire Tobias](https://www.linkedin.com/in/cesaire-tobias-5555a274/)

This book is for readers from diverse backgrounds (economists, statisticians, engineers, and beyond) who want to produce advanced analytics workflows but don't necessarily have computer science foundations. Rather than teaching you how to code, it focuses on setting up the technical infrastructure that supports modern data science work.

## Chapters

The book runs in three parts, in rough dependency order.

### Foundations

1. **The Command Line**: shells, navigation, redirection and pipes, package managers
2. **Python and R**: installing both, Miniforge, Jupyter, and choosing between them
3. **Data Stores: SQL and Beyond**: SQLite, Parquet, DuckDB, Polars, PostgreSQL, and where credentials belong
4. **Reproducible Environments**: uv, conda, renv, lockfiles, and connecting an environment to your tools
5. **Editors and Version Control**: VS Code, RStudio, Git, GitHub, and `.gitignore`

### Communicating Results

6. **Data Science Tools for Reporting**: Markdown, Quarto, R Markdown, LaTeX, Typst, and parameterised reports
7. **Data Visualisation**: matplotlib, seaborn, plotly, ggplot2, and Mermaid diagrams
8. **Cloud Platforms for Data Science**: rented compute and storage, cost control, and access management

### Shipping Your Work

9. **Web Development for Data Scientists**: Shiny, Dash, Streamlit, and Flask for interactive apps
10. **Containerisation**: Docker, Compose, and image hygiene
11. **Deploying Data Science Projects**: Render, Cloud Run, Posit Connect Cloud, and CI-driven deploys
12. **Optimising Workflows and Next Steps**: project layout, Make, testing, DVC, and CI

Plus two appendices: utility tools worth knowing about, and a troubleshooting reference.

## Read Online

The book is published via GitHub Pages at [ces0491.github.io/rbr](https://ces0491.github.io/rbr/).

## Building Locally

This is a [Quarto](https://quarto.org/) book project. To build it locally:

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (>= 1.4)
- [Python 3.13+](https://www.python.org/) with Jupyter (`pip install jupyter nbformat nbclient`) — matches the version CI uses
- [R 4.4+](https://cran.r-project.org/) with packages: `knitr`, `rmarkdown`, `reticulate`, `tidyverse`, `shiny`, `plotly`, `lubridate`

### Render

```bash
# HTML (default)
quarto render

# Preview with live reload
quarto preview
```

Output is written to the `output/` directory.

`execute: freeze: auto` in `_quarto.yml` means a chapter is only re-executed when its source changes; cached results live in `_freeze/`, which is gitignored. CI therefore has no cache and executes every chapter from scratch on each publish, which is why the workflow installs the full R and Python toolchain.

### PDF / EPUB

PDF and EPUB require Chromium (for Mermaid diagrams) and TinyTeX. These formats are disabled in CI but can be generated locally by uncommenting the relevant sections in `_quarto.yml` and running:

```bash
quarto render --to pdf
quarto render --to epub
```

## Project Structure

```
.
├── _quarto.yml          # Book configuration
├── index.qmd            # Welcome & preface
├── chapters/            # Chapter source files (.qmd)
├── assets/              # Cover images
├── data/                # Data files used in examples
├── references.bib       # Bibliography
├── .github/workflows/   # CI/CD — publishes to GitHub Pages on push to main
└── LICENSE              # CC BY-NC-SA 4.0
```

## License

The book content is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Code examples are provided under the MIT License.
