# Yee Chin — portfolio

A pixel, space-themed portfolio. Fly a little astronaut around a solar system;
walk up to a planet to zoom it, then press **Space** (or tap) to open that
section. On phones an on-screen D-pad appears.

Everything is a single self-contained file — `index.html`. No build, no
dependencies, no image files (all art is CSS + inline SVG). Fonts load from
Google Fonts.

## Run locally

Just open `index.html` in a browser. Or serve it:

```bash
cd portfolio-website
python3 -m http.server 8000   # then visit http://localhost:8000
```


## Custom domain (optional)

Netlify → https://app.netlify.com/projects/yeechin-portfolio/deploys

## Editing content

All the section copy lives in the `content` object near the bottom of
`index.html` (`education`, `work`, `projects`, `hobbies`, `volunteering`,
`socials`).
Planet colours/positions are in the CSS (`#education`, `#work`, …) and the
`PLANET_ART` object.
