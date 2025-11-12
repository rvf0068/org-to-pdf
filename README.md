# Org → PDF CI

This repository demonstrates a GitHub Actions workflow that converts Emacs Org-mode files (.org) to PDF automatically.

How it works
- On push of any `*.org` file (or on manual dispatch), the workflow:
  - Installs Emacs quickly using purcell/setup-emacs.
  - Installs a small, cached TeX Live via latex-actions/setup-texlive with the packages required for tikz, amsmath and bibliography.
  - Runs Emacs in batch mode to export each `.org` file to PDF (using latexmk so bibliographies and tikz work).
  - Uploads the created PDFs as a workflow artifact named `exported-pdfs`.

Notes
- If a build complains about a missing LaTeX package, add that package name to the `extra-packages` list in the workflow step `Setup TeX Live` (or set scheme to medium/full).
