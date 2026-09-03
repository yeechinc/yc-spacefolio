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

## Deploy to Netlify

### Option A — drag & drop (fastest)

1. Go to https://app.netlify.com/drop
2. Drag the whole `portfolio-website` folder onto the page.
3. Done — you get a `random-name.netlify.app` URL. Rename it under
   **Site settings → Change site name**.
4. To update later: drag the folder again onto **Deploys**.

### Option B — connect a Git repo (auto-deploys on every push)

1. Create the repo (from inside this folder):

   ```bash
   cd portfolio-website
   git init
   git add .
   git commit -m "Pixel space portfolio"
   git branch -M main
   git remote add origin https://github.com/yeechinc/portfolio-website.git
   git push -u origin main
   ```

   > Note: there is an accidental `git` repo at `~/.git` on this machine.
   > It doesn't break anything here (Git uses the closest `.git`, which will be
   > this folder's), but you may want to clean it up separately.

2. On Netlify: **Add new site → Import an existing project → GitHub →**
   pick `portfolio-website`.
3. Build command: *(leave empty)*. Publish directory: `.`
   (`netlify.toml` already sets this.)
4. Deploy. Every `git push` now redeploys.

## Custom domain (optional)

Netlify → **Domain settings → Add a domain**. If you buy one (e.g. from
Namecheap/Cloudflare), point it at Netlify with their nameservers or an
`ALIAS`/`CNAME` record — Netlify walks you through it and provisions HTTPS.

## Editing content

All the section copy lives in the `content` object near the bottom of
`index.html` (`education`, `work`, `projects`, `hobbies`, `volunteering`,
`socials`).
Planet colours/positions are in the CSS (`#education`, `#work`, …) and the
`PLANET_ART` object.
