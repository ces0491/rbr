# Ready Before Run()

A Practical Guide to Gear Up for Data Science, by [Cesaire Tobias](https://www.linkedin.com/in/cesaire-tobias/)

This book is for readers from diverse backgrounds (economists, statisticians, engineers, and beyond) who want to produce advanced analytics workflows but don't necessarily have computer science foundations. Rather than teaching you how to code, it focuses on setting up the technical infrastructure that supports modern data science work.

## Chapters

The book runs in three parts, in rough dependency order. Numbers match the rendered book, which counts the Welcome page as chapter 1 and the Introduction as chapter 2.

### Foundations

3. **The Command Line**: shells, navigation, redirection and pipes, package managers
4. **Python and R**: installing both via uv or Miniforge, Jupyter, and choosing between them
5. **Editors and Version Control**: VS Code, RStudio, Git, GitHub, and `.gitignore`
6. **Data Stores: SQL and Beyond**: SQLite, Parquet, DuckDB, Polars, PostgreSQL, and where credentials belong
7. **Reproducible Environments**: uv, conda, renv, lockfiles, and connecting an environment to your tools

### Communicating Results

8. **Data Science Tools for Reporting**: Markdown, Quarto, R Markdown, LaTeX, Typst, and parameterised reports
9. **Data Visualisation**: matplotlib, seaborn, plotly, ggplot2, and Mermaid diagrams

### Shipping Your Work

10. **Cloud Computing for Data Science**: rented compute and storage, cost control, and access management
11. **Web Development for Data Scientists**: Shiny, Dash, Streamlit, and Flask for interactive apps
12. **Containerisation**: Docker, Compose, and image hygiene
13. **Deploying Data Science Projects**: Render, Cloud Run, Posit Connect Cloud, and CI-driven deploys
14. **Optimising Workflows and Next Steps**: project layout, Make, testing, DVC, and CI

Plus three appendices: utility tools worth knowing about, a troubleshooting reference, and the changelog.

## Read Online

The book is published at [rbr.sheetsolved.com](https://rbr.sheetsolved.com/), served from GitHub Pages via the `CNAME` file in the repository root.

## Editions

The book is revised as the tools change. Each published edition is numbered by year and month (`2026.10`), with a `.1` suffix for a second release in the same month, and the Changelog appendix records what each edition changed. [SCOPE.md](SCOPE.md) lists the checks an edition has to pass.

To publish an edition:

1. Run the checks in `SCOPE.md`.
2. Set `version` in `_variables.yml` and `date` in `_quarto.yml`.
3. Add the edition's entry to `chapters/changelog.qmd`.
4. Commit, tag the commit (`git tag -a v2026.10 -m "Edition 2026.10"`), and push the commit and the tag.

CI publishes the site on every push to `main`; the tag marks which commit an edition was.

## Building Locally

This is a [Quarto](https://quarto.org/) book project. To build it locally:

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (>= 1.4)
- [Python 3.13+](https://www.python.org/) with Jupyter (`pip install jupyter nbformat nbclient`) — matches the version CI uses
- [R 4.5+](https://cran.r-project.org/) with `knitr`, `rmarkdown` and `reticulate`

That R list is short because every code example in the book is `eval: false` — the examples are there to be read and copied into your own project, not run during the build. The one chunk that does execute, the Mermaid generator in the Visualisation chapter, uses base R. `reticulate` is needed even so: knitr loads it whenever a document contains a Python chunk, whether or not that chunk runs. If you switch an example to `eval: true`, install its packages and add them to `.github/workflows/publish.yml`.

### Render

```bash
# HTML (default)
quarto render

# Preview with live reload
quarto preview
```

Output is written to the `output/` directory.

`execute: freeze: auto` in `_quarto.yml` means a chapter is only re-executed when its source changes; cached results live in `_freeze/`, which is gitignored. CI therefore has no cache and processes every chapter from scratch on each publish, which is why the workflow installs the R and Python toolchains even though almost nothing in the book executes.

### PDF / EPUB

Both formats need a headless browser to draw the Mermaid diagrams (`quarto install chrome-headless-shell`), and PDF also needs TinyTeX (`quarto install tinytex`). They are disabled in CI but can be generated locally by uncommenting the relevant sections in `_quarto.yml` and running:

```bash
quarto render --to pdf
quarto render --to epub
```

## Project Structure

```
.
├── _quarto.yml          # Book configuration
├── _variables.yml       # Edition number shown in the book
├── SCOPE.md             # Checks every edition has to pass
├── CNAME                # Custom domain; listed under project resources so
│                        #   `quarto publish` copies it into the output
├── index.qmd            # Welcome & preface
├── chapters/            # Chapter source files (.qmd)
├── assets/              # Cover image, used as both cover and favicon
├── data/                # Data files used in examples
├── references.bib       # Bibliography
├── .github/workflows/   # CI/CD — publishes to GitHub Pages on push to main
└── LICENSE              # CC BY-NC-SA 4.0
```

## License

The book content is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Code examples are provided under the MIT License.
