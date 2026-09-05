# Contributing

This repository is a personal learning path, developed together with a mentor.
It's not set up to take external pull requests, but the guidelines below keep
the project consistent for anyone (mentor included) working in it.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt        # runtime deps for all notebooks
pip install -r requirements-dev.txt    # pre-commit, nbstripout
pre-commit install
```

Each paper folder also has its own `requirements.txt` if you only want the
dependencies for that one notebook.

## Before committing

- Run `pre-commit install` once per clone. It strips notebook outputs
  (via `nbstripout`) automatically on commit, so diffs stay readable and the
  repo doesn't accumulate binary output blobs.
- If you add a new paper implementation, update the paper table in the root
  [ReadMe.md](ReadMe.md) and add a `requirements.txt` in the paper's folder if
  it needs packages beyond the root `requirements.txt`.
- Keep large datasets and generated artifacts out of git — see `.gitignore`.
  Data should be downloaded by the notebook, not committed.

## Style

- Notebook and folder names: lowercase-with-underscores or PascalCase per the
  existing convention in that section, no typos where avoidable.
- Prefer clear naming and inline comments only where the "why" isn't obvious
  from the code itself.
