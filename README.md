# Ready Before Run()

A Practical Guide to Gear Up for Data Science, by [Cesaire Tobias](https://www.linkedin.com/in/cesaire-tobias-5555a274/)

This book is for readers from diverse backgrounds (economists, statisticians, engineers, and beyond) who want to produce advanced analytics workflows but don't necessarily have computer science foundations. Rather than teaching you how to code, it focuses on setting up the technical infrastructure that supports modern data science work.

## Chapters

1. **Setting Up for Success**: command line, Python, R, SQL, IDEs, and Git
2. **Data Science Tools for Reporting**: Markdown, Quarto, R Markdown, LaTeX, and parameterised reports
3. **Data Visualisation**: matplotlib, seaborn, plotly, ggplot2, and Mermaid diagrams
4. **Cloud Computing for Data Science**: cloud platforms, costs, and data residency
5. **Web Development for Data Scientists**: Shiny, Dash, Streamlit, and Flask for interactive apps
6. **Deploying Data Science Projects**: Render, Fly.io, Cloud Run, shinyapps.io, and CI-driven deploys
7. **Containerisation**: Docker, Compose, and reproducible environments
8. **Optimising Workflows and Next Steps**: project layout, Make, DVC, and CI/CD
9. **Utility Tools for Data Scientists**: AI coding assistants, modern CLI tooling, and day-to-day productivity aids

Plus a troubleshooting appendix and curated references.

## Read Online

The book is published via GitHub Pages at [ces0491.github.io/rbr](https://ces0491.github.io/rbr/).

## Building Locally

This is a [Quarto](https://quarto.org/) book project. To build it locally:

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (>= 1.3)
- [Python 3.12+](https://www.python.org/) with Jupyter (`pip install jupyter nbformat nbclient`)
- [R 4.4+](https://cran.r-project.org/) with packages: `knitr`, `rmarkdown`, `reticulate`, `tidyverse`, `shiny`, `plotly`, `lubridate`

### Render

```bash
# HTML (default)
quarto render

# Preview with live reload
quarto preview
```

Output is written to the `output/` directory.

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
