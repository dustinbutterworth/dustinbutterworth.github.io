# dustinbutterworth.github.io

Personal site for [www.dustinbutterworth.com](https://www.dustinbutterworth.com) — Astro static site deployed to GitHub Pages.

## Local development

Requires **Node.js ≥ 22.23.4** (Astro 7).

```bash
npm install
npm run dev
```

```bash
npm run build
npm run preview
```

## Resume PDF

`public/resume.pdf` is a **static asset**. This repo does not generate the resume.

Refresh it from the sibling [`json_resume`](../json_resume) project:

```bash
cd ../json_resume
npm run build
npm run publish-resume
```

Then follow the printed git steps in this repo to commit and push when you want the live site updated.

## Deploy

Pushes to `master` run `.github/workflows/deploy.yml` (build Astro → GitHub Pages). Custom domain is set via `public/CNAME` (`www.dustinbutterworth.com`).

In the GitHub repo settings, enable **Pages → Source: GitHub Actions** if it is not already.

CI uses commit-SHA-pinned Actions, job-scoped token permissions, and Dependabot (`.github/dependabot.yml`) for npm + Actions updates.

Enable GitHub **Secret scanning** and **Push protection** (free for public repos) under **Settings → Code security → Secret scanning**. That is a GitHub setting, not a file in this repo.
