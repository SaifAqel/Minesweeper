# Minesweeper 
by Saif Aqel  

Live demo: https://saifaqel.github.io/Minesweeper/  

A compact, single-file Minesweeper in plain HTML/CSS/JS — no frameworks or build tools. Fully responsive, works on desktop and mobile, supports keyboard controls, and allows seeded boards for repeatable challenges.

## Features
- **Single file**: All code in index.html — easy to host anywhere.
- **Presets**: Beginner (9×9, 10), Intermediate (16×16, 40), Expert (30×16, 99).
- **Custom boards**: Set width/height/mines (safe limits applied).
- **Safe first click**: First move and 3×3 area are mine-free.
- **Seeded RNG**: Generate reproducible boards from a seed string.

### Controls:
- Left-click/tap to reveal
- Right-click/long-press to flag
- Double-click/chord on numbers to reveal neighbors
- **Keyboard**: Arrows to move, Space/Enter to reveal/chord, F to flag, R to restart
- **Mobile support**: Long-press to flag.

### UI details:
- Mine counter, timer (up to 999s), optional question marks, animated face.
- Progress tracking: Best time per layout stored in localStorage.
- Accessibility: ARIA roles, roving tab index, clear focus indicators.

## Quick Start (Local)
Download or copy index.html.  

Open in your browser, or run:

```bash
python -m http.server
# Visit http://localhost:8000/
```

## Deploy
**GitHub Pages**: Place index.html at repo root → Settings → Pages → Deploy from branch → main → root.  

**Other hosts**: Upload to Netlify, Vercel, S3, etc.  

Live site: https://saifaqel.github.io/Minesweeper/  

## Project Structure
```css
minesweeper/
└── index.html   # all HTML, CSS, JS
```

## Technical Notes
- Deterministic RNG: xmur3 (hash) + mulberry32 (PRNG).
- Mines placed and neighbor counts generated after first click.
- Flood-reveal for empty areas uses a stack (no recursion).
- Best times saved with layout-specific keys.

## License
MIT License — see LICENSE.
