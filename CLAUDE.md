# CLAUDE.md — Project Instructions for Claude Code

## Project Overview
Personal academic website for PD Dr. Steven R. Talbot (Preclinical Data Science, Hannover Medical School / MHH).
- **Domain:** talbotsr.com
- **Framework:** Quarto (`_quarto.yml`)
- **Output:** `docs/` (gitignored — built by CI)
- **Repo:** https://github.com/mytalbot/mytalbot.github.io (branch: `master`)

## Deployment
- Push to `master` triggers GitHub Actions (`.github/workflows/publish.yml`)
- CI renders the site with Quarto + R, then deploys to **GitHub Pages**
- Custom domain via `CNAME` file (included as a Quarto resource)
- **Do NOT** render locally before pushing — CI handles it
- **Do NOT** commit the `docs/` folder

## Project Structure
```
_quarto.yml          # Site config (navbar, theme, bibliography)
styles.css           # Custom CSS
references.bib       # BibTeX bibliography
apa.csl              # Citation style
CNAME                # Custom domain (talbotsr.com)
index.qmd            # Home page
publications.qmd     # Publications page
talks.qmd            # Talks page
teaching.qmd         # Teaching page
tools.qmd            # Tools & Apps page
blog.qmd             # Blog listing page
impressum.qmd        # Legal notice (German)
datenschutz.qmd      # Privacy policy (German)
posts/               # Blog posts (each in YYYY-MM-DD-slug/index.qmd)
posts/_metadata.yml  # Shared blog post metadata (author, freeze: true)
images/              # Site images
```

## Blog Posts
- Location: `posts/YYYY-MM-DD-slug/index.qmd`
- Shared defaults in `posts/_metadata.yml` (author info, `freeze: true`, `code-fold: true`)
- Posts can include R/Python code chunks; outputs are frozen by default

## Key Conventions
- Theme: `cosmo` with custom `styles.css`
- Bibliography: APA style (`apa.csl`) from `references.bib`
- Code folding enabled globally
- Footer includes Impressum and Datenschutz (German legal requirements)
- Language: Site content is English; legal pages are German

## Workflow
1. Edit `.qmd` files
2. Optional: `quarto preview` to check locally
3. `git add`, `git commit`, `git push origin master`
4. GitHub Actions builds and deploys automatically
