# msilabs.github.io

Source of the [msilabs](https://msilabs.github.io) website, built with [Alo](https://github.com/msilabs/alo).

## Develop

Requires Node.js 22 or newer.

```bash
npm install
node alo dev
```

Open `http://localhost:3000`. The page reloads when you save a file.

## Build

```bash
node alo build
```

The static site is written to `dist/`.

## Project layout

```
pages/        page.alo (home), not-found.alo, layout.alo
components/   Hero, About, Packages, Learn, Story, Founder, Header, Footer
data/         site.json (name, links, nav), packages.json, story.json
global/       theme.css, base/01-reset.css
public/       files copied as they are (logo.png)
```

To change text or links, edit the files in `data/`. To change the design, edit the matching file in `components/` or `global/`. See `AGENTS.md` for Alo rules.

## Deploy

- **GitHub Pages:** `.github/workflows/pages.yml` builds and deploys on every push to `main`. In the repository settings, set Pages source to **GitHub Actions**.
- **Vercel:** import the repository with Framework Preset **Other**, Install Command `npm ci`, Build Command `npm run build`, Output Directory `dist`.
