# Org → PDF CI

This repository demonstrates a GitHub Actions workflow that converts Emacs Org-mode files (.org) to PDF automatically.

How it works
- On every push (or on manual dispatch), the workflow:
  - Installs Emacs quickly using purcell/setup-emacs.
  - Installs a minimal TeX Live distribution using teatimeguest/setup-texlive-action with caching for speed.
  - Runs Emacs in batch mode to export each `.org` file to PDF (using latexmk so bibliographies and tikz work).
  - Commits the generated PDF files back to the repository.
  - Uploads the created PDFs as a workflow artifact named `exported-pdfs`.

Notes
- If a build complains about a missing LaTeX package, add that package name to the `packages` list in the "Setup TeX Live" step.
