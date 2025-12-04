# Roam Photos Web Gallery

This repository contains web exports of photos from the Roam project, automatically deployed via GitHub Pages.

## Viewing

Visit the live site at: https://uniyatra.github.io/roam-web/

The root page provides links to all available photo galleries.

## Update Process

This site is automatically updated when running:
```bash
python scripts/roam_photos.py web --output-name export-name --has-gps --fields url,date,gps [options]
```

The export process:
1. Generates a ZIP file in `output/photos/`
2. Extracts contents to named subdirectory: `export-name/`
3. Encrypts gallery with StatiCrypt password protection
4. Regenerates root `index.html` with links to all galleries
5. Commits and pushes to GitHub

## Structure

- `index.html` - Auto-generated index with links to all galleries
- `summer-2024/` - Example export subdirectory
  - `index.html` - Gallery page (password protected)
  - `assets/css/` - Stylesheets
  - `assets/photos/` - WebP photo thumbnails (300x300px)
  - `assets/maps/` - Static map images from Google Maps

## Password Protection

All galleries are protected with StatiCrypt client-side encryption. Enter the password when prompted to view photos.
