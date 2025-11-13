# Org → PDF CI

This repository demonstrates a GitHub Actions workflow that converts Emacs Org-mode files (.org) to PDF automatically.

How it works
- On every push (or on manual dispatch), the workflow:
  - Installs Emacs quickly using purcell/setup-emacs.
  - Installs TeX Live via Ubuntu's package manager with the packages required for tikz, amsmath and bibliography.
  - Runs Emacs in batch mode to export each `.org` file to PDF (using latexmk so bibliographies and tikz work).
  - Commits the generated PDF files back to the repository.
  - Uploads the created PDFs as a workflow artifact named `exported-pdfs`.

Notes
- If a build complains about a missing LaTeX package, install it using `sudo apt-get install` in the "Install TeX Live" step.
