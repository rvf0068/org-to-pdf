# Org → PDF CI

This repository demonstrates a GitHub Actions workflow that converts Emacs Org-mode files (.org) to PDF automatically.

How it works
- On push of any `*.org` file (or on manual dispatch), the workflow:
  - Installs Emacs and TeX Live directly from Ubuntu's package repository.
  - Runs Emacs in batch mode to export each `.org` file to PDF (using latexmk so bibliographies and tikz work).
  - Uploads the created PDFs as a workflow artifact named `exported-pdfs`.

Notes
- If a build complains about a missing LaTeX package, install it by adding the appropriate `texlive-*` package to the apt-get install command in the workflow.
