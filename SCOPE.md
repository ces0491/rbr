# SCOPE — Ready Before Run()

## Purpose

Get readers who came to data work from economics, statistics, engineering or science set up with the infrastructure data science assumes: the command line, environments, version control, reporting, containers and deployment.

## Done

The book is revised as the tools change, so there is no finish line. "Done" applies to each edition, and an edition ships when all of these pass:

- [ ] A clean checkout renders with `quarto render` without render warnings, and the CI publish succeeds.
- [ ] Every example added or changed since the last edition has been run in the shells the text targets (Windows PowerShell 5.1, Git Bash, and bash on macOS or Linux) and does what the text says.
- [ ] Python blocks pass ruff's default rules. A notebook cell whose imports are used by a later cell is the accepted exception.
- [ ] Every link resolves, apart from sites that block automated requests.
- [ ] Dated claims (platform availability, deprecations, version pins, licence thresholds) have been checked against the provider's own page or registry.
- [ ] The prose meets the house style: plain declaratives, no hyperbole or filler, nothing said twice, and quantifiers backed by evidence.
- [ ] `version` in `_variables.yml`, `date` in `_quarto.yml`, the changelog entry and the git tag agree on the edition, and the README matches the release.

## Out of scope

- Teaching statistics, modelling methods or how to code. The book covers what has to be in place before that code can run.
- Printed prices and free-tier allowances. Each platform says what it bills for and links to its pricing page; licence thresholds and technical limits are the exceptions.
- Covering every tool. Each chapter covers the ones a reader is most likely to need, with uv leading and conda in parallel.
- PDF and EPUB builds in CI.

## Bar

Production. Readers come from non-CS backgrounds and can't debug a broken example, so an example that fails as written is the most serious defect an edition can ship with, ahead of any prose issue.

## Decision

The author, Cesaire Tobias, signs off each edition before it's tagged and pushed to `main`.

## Revision history

- 2026-10-28: initial scope, adopted with calendar versioning (edition 2026.10).
