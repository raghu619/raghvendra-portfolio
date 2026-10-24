# raghvendra-portfolio

Personal portfolio of Raghvendra Rao Koduri: case studies of AI engineering projects built on real data.

Plain HTML and CSS with one small script, no build step. Hosted on Vercel's free Hobby plan; every push to `main` redeploys.

## Structure

- `index.html`: home page
- `projects/<name>/index.html`: one case study per project (served at `/projects/<name>/`)
- `notes/<name>/index.html`: standalone interactive explainers (served at `/notes/<name>/`), each with its own inline styles and script
- `styles.css`: all styles; `shelve.js`: the interactive listings on the catalogue case study
- `assets/<project>/`: charts, copied from each project's repo
- `og-home.png`, `assets/<project>/og-<project>.png`: 1200x630 link-preview cards, used when a page is shared on LinkedIn
- `fonts/`: self-hosted Archivo and Source Serif 4, plus STIX Two Text, IBM Plex Sans and JetBrains Mono for the notes (all SIL Open Font License, see the licence files)

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Vercel project settings: project name `raghvendra-rao-koduri` (it sets the domain), framework preset **Other**, no build command, output directory left empty (the repo root is the site). `vercel.json` adds trailing slashes so `/projects/<name>` and `/projects/<name>/` resolve to the same page.

The social preview tags (`og:url`, `og:image`) in both HTML pages point at `https://raghvendra-rao-koduri.vercel.app`. If Vercel gives the project a different domain, change them to match.

## Add a project

1. Copy `projects/catalog-curation/` to `projects/<new-name>/` and replace the content.
2. Put its charts in `assets/<new-name>/`.
3. Add a work item to `index.html`.
