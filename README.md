# Coralie Rousseau — Jupyter Book Website

A Jupyter Book website using [MyST Markdown](https://mystmd.org/), based on the [chicago-aiscience.github.io](https://github.com/chicago-aiscience/chicago-aiscience.github.io) structure.

## Project Structure

```
.
├── docs/                    # Source content directory
│   ├── index.md             # Homepage
│   ├── about.md             # About page
│   ├── myst.yml             # MyST site configuration
│   ├── images/              # Image assets
│   └── styles/              # Custom CSS
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions deployment
├── pyproject.toml           # Python dependencies
├── Makefile                 # Development commands
└── README.md
```

## Prerequisites

- **Python 3.11+**
- **uv** (optional, recommended) — [installation](https://github.com/astral-sh/uv#installation)
- **Node.js 18.x+** — used by GitHub Actions for deployment

## Local Development

### Install dependencies

```bash
# With uv (recommended)
uv sync

# Or with pip
pip install "jupyter-book>=2.1.0" "nbconvert>=7.17.0"
```

### Build and serve

```bash
make install   # Install dependencies
make serve    # Build and serve at http://localhost:8000
```

Or manually:

```bash
cd docs
jupyter book start
```

### Build only

```bash
make build
# Output in docs/_build/html/
```

## GitHub Pages Deployment

1. Push this repo to GitHub
2. Go to **Settings** → **Pages**
3. Under **Source**, select **GitHub Actions**
4. Pushes to `main` will trigger deployment

### Base URL

- **User/org site** (`coralie_rousseau.github.io`): keep `BASE_URL: ''` in `.github/workflows/deploy.yml`
- **Project site** (`username.github.io/coralie_rousseau`): set `BASE_URL: '/coralie_rousseau'`

## Adding Content

1. Create Markdown files in `docs/`
2. Add them to `docs/myst.yml` under `toc`
3. Use MyST directives: `:::{card}`, `::::{grid}`, `:::{note}`, etc.

## Resources

- [Jupyter Book](https://jupyterbook.org/)
- [MyST Markdown](https://mystmd.org/guide)
- [GitHub Pages](https://docs.github.com/en/pages)
