# Portfolio — Quarto draft

This is a draft conversion of your GitHub Pages README into a Quarto website. Structure:

```
portfolio-quarto/
├── _quarto.yml          # site config: navbar, theme, output dir
├── index.qmd            # homepage (hero, bio, links)
├── data-science.qmd     # Data Science & Finance projects
├── bioinformatics.qmd   # Bioinformatics & Genomics projects
├── upcoming.qmd         # Upcoming projects + future plans
├── styles/
│   ├── custom.scss      # Bootstrap/theme variable overrides (colors, fonts)
│   └── custom.css       # project-card, hero, and section styling
└── images/              # add your existing images here (see below)
```

## To get this running locally

1. **Install Quarto** (not available in this sandbox, so this step happens on your machine): https://quarto.org/docs/get-started/
2. **Add your images** into `images/`, using these exact filenames (referenced in the `.qmd` files) — rename or symlink from your existing repo:
   - `headshot_natural.png`
   - `weather_website_gif.gif`
   - `gbp_rupiah.gif`
   - `newsShield.gif`
   - `vinfast_gif.gif` (optional — currently not placed on a page; add if you want a second image on the NewsShield card)
   - `atac_dna.webp` (from your `ATAC DNA.webp`)
   - `gene_expression.jpeg` (from your `gene expression.jpeg`)
   - `nature.jpg`
   - `dna_methylation.jpg` (from your `dna methylation.jpg`)
3. **Preview locally**: `quarto preview` from the project root — this opens a live-reloading local server.
4. **Add an Education page** if you want to keep that link working: create `Education.qmd` with a `title:` header and your content, or update the `index.qmd` link to point elsewhere.

## Publishing to GitHub Pages

Since your repo is `Thomas-Nguyen12.github.io` (a user-pages repo), the simplest path:

1. `_quarto.yml` is already set to `output-dir: docs`.
2. Run `quarto render` — this builds the site into a `docs/` folder.
3. Commit and push, then in your repo's **Settings → Pages**, set the source to the `docs/` folder on your default branch.

Alternatively, run `quarto publish gh-pages` to have Quarto build and push to a `gh-pages` branch automatically (then point Pages at that branch instead).

## What changed from the original README

- Split one long page into a navbar with 4 pages (Home / Data Science / Bioinformatics / Upcoming)
- Each project is now a styled "card" (`.project-card` div) instead of a stacked block, with a fixed-height cropped image
- The "results pending publication" note is now a proper `callout-important` block instead of a blockquote
- The "under development" note is a `callout-warning` block
- Skills are rendered as pill-style badges in the hero section
- Theme is Bootstrap's `cosmo` with your own SCSS overrides (accent blue `#2563eb`, Inter font)

Everything else — your text, links, and image references — is carried over as-is.
