# Articulate Documentation Site

The public documentation site for [Articulate](https://github.com/articulate-orm/core), built with [Astro Starlight](https://starlight.astro.build) and deployed at the org-root Pages domain: **https://articulate-orm.github.io/**.

This repo is the dedicated `articulate-orm/articulate-orm.github.io` Pages repo (GitHub's org/user-root Pages convention — the repo name must match exactly). Docs content originated in `articulate-orm/core` PR #35 and was relocated here so the site can live at the clean root URL instead of a `/core` subpath, and so old doc versions can be preserved independently of the code repo (which only keeps current-code state).

## Structure

- `src/content/docs/index.mdx` — landing page (hero + feature cards).
- `src/content/docs/concepts/` — core concepts (context-bounded entities, unit of work, hydration, caching).
- `src/content/docs/guides/` — task-oriented guides (getting started through known limitations), adapted from `articulate-demo/documentation/`.
- `src/content/docs/architecture/` — module map and Deptrac boundaries/conventions, adapted from the core repo's `CLAUDE.md`.
- `src/content/docs/reference/` — ADRs and the changelog.
- `src/content/docs/1.0/` — archived `1.0` snapshot of the docs, managed by the [`starlight-versions`](https://starlight-versions.vercel.app) plugin.
- `astro.config.mjs` — Starlight sidebar, site metadata, and the `starlight-versions` plugin config (version switcher).
- `src/styles/custom.css` — light/airy accent palette overrides.

## Versioning

This site uses the [`starlight-versions`](https://starlight-versions.vercel.app) Starlight plugin to give the header a version-switcher dropdown. To cut a new archived version, add a new entry to the `versions` array in `astro.config.mjs` and run `npm run dev` once locally — the plugin archives the current docs tree under the new version's slug. See the plugin's ["Create a New Version"](https://starlight-versions.vercel.app/guides/create-new-version/) guide.

## Development

```bash
npm install
npm run dev       # local dev server
npm run build     # static build to dist/
npm run preview   # preview the production build
```

## Deployment

Pushes to `main` are built and deployed to GitHub Pages by `.github/workflows/deploy.yml`, using `actions/deploy-pages`. GitHub Pages must have **Source: GitHub Actions** selected in repo Settings → Pages.
