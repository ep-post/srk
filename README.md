# shafiqrkhan.net

Personal website for Shafiqur Rahman Khan — social entrepreneur, anti-trafficking advocate, and founder of [Empower People](https://www.empowerpeople.in).

## Structure

Static site, no build step, no framework — plain HTML/CSS.

```
.
├── index.html            Home
├── bio.html               Bio
├── marches.html           The Marches
├── empower-people.html    Empower People (organisation)
├── teaching.html          Teaching
├── media.html              Interviews & Media
├── contact.html            Contact
├── styles.css              Shared stylesheet for all pages
└── images/                 All site photos
```

Every page shares `styles.css`, so a palette, type, or layout change in that one file updates the whole site.

## Local preview

No build tools needed — just open `index.html` directly in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying

This repo deploys as-is to any static host (Netlify, GitHub Pages, Vercel, Cloudflare Pages). No build command or publish directory beyond the repo root is required.

### GitHub Pages (recommended: push with git, not drag-and-drop)

Uploading files individually through the GitHub website's "Add file" button often drops the `images/` folder structure, which results in broken photos on the live site. Push with git instead:

```bash
# from inside this folder
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source → Deploy from a branch → `main` / `(root)`**.

The repo already includes a `.nojekyll` file, which tells GitHub Pages to serve the files exactly as they are instead of running them through Jekyll — this avoids a class of GitHub Pages bugs where static assets silently fail to publish.

After pushing, GitHub Pages can take 1–2 minutes to build. If photos still don't show up, check the repo's file list on github.com and confirm the `images/` folder is there with all 22 `.jpg` files inside.

### Netlify

Drag the folder onto the deploy area, or connect the repo with build command left blank and publish directory set to `/`.

## Editing content

- Text content lives directly in each page's HTML.
- Photos live in `images/`; reference them as `images/filename.jpg`.
- Shared elements (nav, footer) are duplicated across each HTML file — update all seven when changing them.
