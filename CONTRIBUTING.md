# Contributing

Thanks for taking an interest in the AI Researcher Learning Path! This repo
tracks my progress working through core AI/ML papers from scratch
with my mentor — from Transformers and BERT up through diffusion, RLHF, and
retrieval systems. It's primarily a personal study log, but if you're a fellow learner this doc is for you.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt        # runtime deps for all notebooks
pip install -r requirements-dev.txt    # pre-commit, nbstripout
pre-commit install
```

Each paper folder under `essentials/`, `foundation/`, `high/`, and
`recommended/` also has its own `requirements.txt` if you only want to run
that one notebook.

## Before committing

- Run `pre-commit install` once per clone — it strips notebook outputs
  (`nbstripout`) automatically on commit, keeping diffs readable.
- Implementing a new paper? Add a row to the paper table in the root
  [ReadMe.md](ReadMe.md) and drop a `requirements.txt` in its folder if it
  needs anything beyond the root `requirements.txt`.
- Keep datasets and generated artifacts out of git (see `.gitignore`) —
  notebooks should download data themselves, not commit it.

## Style

- Match the existing naming convention for the section you're in, and avoid
  typos in folder/file names where you can.
- Skip comments that just restate what the code does; only comment on the
  non-obvious "why".

Thanks for reading this far — happy to have you looking through the work!
