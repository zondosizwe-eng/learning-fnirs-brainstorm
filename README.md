# Learning fNIRS with Brainstorm/NIRSTORM

This repository is the MkDocs source for an 18-lesson practical fNIRS course based on the Brainstorm/NIRSTORM finger-tapping tutorial.

## Current release

- Lessons 1–16 document the completed single-participant workflow.
- Lessons 17–18 are clearly marked **Coming later** until the five-participant replication and group-analysis extension have been completed.
- The package includes the final HbO/HbR reconstruction figures, troubleshooting record, glossary, workflow table and hidden-answer MCQs.
- The acknowledgements page links the official NIRSTORM tutorial and the primary NIRSTORM, optical-tomography workflow and Brainstorm publications.
- The project is configured for publication with Read the Docs and includes a direct-file offline-preview configuration.

## Run locally

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
mkdocs serve
```

Open `http://127.0.0.1:8000` in a browser. Build the static site with `mkdocs build --strict`.

## Build the downloadable offline preview

The ordinary Read the Docs build uses web-friendly directory URLs. For a preview
that can be opened directly from a downloaded folder, use:

```bash
mkdocs build --strict -f mkdocs-preview.yml
```

This creates `site-preview/` with direct `.html` links that work without a local
web server.

## Publish with Read the Docs

The repository already contains the required `.readthedocs.yaml` configuration. Follow [`PUBLISHING_READTHEDOCS.md`](PUBLISHING_READTHEDOCS.md) after reviewing the draft locally.

## Important editing locations

- `mkdocs.yml` controls the navigation, theme and extensions.
- `docs/index.md` is the home page.
- `docs/lessons/` contains the 18 lesson pages.
- `docs/assets/images/` contains teaching figures.
- `docs/assets/stylesheets/extra.css` contains the course styling.

