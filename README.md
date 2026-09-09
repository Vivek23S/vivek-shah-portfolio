# vivek-shah-portfolio

Built with [Astro](https://astro.build). Static output, no server required.

## Local development

```
npm install
npm run dev
```

Visit http://localhost:4321

## Structure

```
src/
  layouts/Base.astro       shared page shell (nav, fonts, footer)
  components/Nav.astro     top navigation
  styles/global.css        color/type tokens, layout grid, "horizon rule" divider
  pages/
    index.astro             home
    research/index.astro    MS vs PhD overview
    research/ms.astro        MS thesis detail
    research/phd.astro       PhD research detail
    campaigns/index.astro    interactive Leaflet map of field sites
    projects/index.astro     coursework / internship projects
    publications/index.astro CV + publications
    gallery/index.astro      photo grid placeholder
public/
  cv-vivek-shah.pdf        <- add your CV here, filename must match publications page link
  gallery/                  <- add photos here
```

## Deploying to GitHub Pages

1. Create a new GitHub repo. Two options:
   - Repo named `<your-username>.github.io` → site is served at the root, keep
     `base: '/'` in `astro.config.mjs`.
   - Any other repo name, e.g. `portfolio` → site is served at
     `/portfolio/`, so set `base: '/portfolio'` in `astro.config.mjs` and update
     `site` to match.
2. Push this project to that repo (`main` branch).
3. In the repo on GitHub: **Settings → Pages → Build and deployment → Source →
   GitHub Actions**. The included workflow (`.github/workflows/deploy.yml`)
   will build and deploy automatically on every push to `main`.
4. First deploy takes a couple of minutes. Your site will be live at the URL
   shown in the Pages settings (also shown in the Actions run once it succeeds).

## Adding a custom domain later

1. Buy the domain (Namecheap, Cloudflare, Google Domains, etc).
2. In the repo: **Settings → Pages → Custom domain**, enter it there — GitHub
   will create the `public/CNAME` file automatically (or add it yourself with
   the domain as its only content).
3. At your domain registrar, add either:
   - an `A` record pointing to GitHub Pages' IPs (listed in GitHub's docs), or
   - a `CNAME` record pointing to `<your-username>.github.io`, if using a subdomain.
4. Wait for DNS to propagate (up to a few hours), then enable "Enforce HTTPS"
   in the same Pages settings once available.

## Next content passes

- Swap the campaign map's approximate coordinates for real logged GPS positions
  once you have them.
- Drop real flight/wind-tunnel photos into `public/gallery/` and wire them into
  `gallery/index.astro`.
- Consider exporting 1–2 real Plotly figures (wind/altitude profiles, the
  plunge-damping-vs-mass trend) as static images or embedded JSON to feature on
  the PhD research page.
