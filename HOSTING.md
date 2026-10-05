# Hosting this portfolio (Netlify or GitHub Pages)

This repo is a **static site** — no build step. The live site is served from the **repository root**.

## Site map

| URL path | What it is |
|----------|------------|
| `/` | Landing page — pick interactive or classic site |
| `/interactive/` | Text-adventure portfolio engine |
| `/traditional/` | Classic HTML portfolio (work, blogs, contact) |
| `/images/` | All site images (add your JPGs here) |

Source notes in `Portfolio Pages/` are optional; they are not required to run the site.

---

## Option A — Netlify (recommended for this project)

**Why it fits well:** Drag-and-drop or Git deploy, automatic HTTPS, custom domain in a few clicks, redirects in `netlify.toml` (already included for old paths).

1. Push this folder to a GitHub/GitLab/Bitbucket repo (or use Netlify Drop).
2. In [Netlify](https://app.netlify.com): **Add new site → Import an existing project**.
3. Build settings:
   - **Build command:** leave empty
   - **Publish directory:** `.` (root)
4. Deploy. Your site URL will look like `https://random-name.netlify.app`.
5. Optional: **Domain settings → Add custom domain** (e.g. `kavya.work`).

**Netlify Drop (no Git):** Zip the project (without `Portfolio Pages/.obsidian` if you want a smaller zip), upload at [app.netlify.com/drop](https://app.netlify.com/drop).

---

## Option B — GitHub Pages

**Why use it:** Free hosting tied to GitHub, good if the repo already lives there and you do not need Netlify extras.

1. Create a GitHub repository and push this project.
2. On GitHub: **Settings → Pages**.
3. **Source:** Deploy from a branch.
4. **Branch:** `main` (or `master`), folder **`/ (root)`**.
5. Save. After a minute or two, the site is at:
   - **User site:** `https://<username>.github.io/` (only if the repo is named `<username>.github.io`)
   - **Project site:** `https://<username>.github.io/<repo-name>/`

`.nojekyll` is included so GitHub does not run Jekyll (which can break plain static files).

**Project site note:** All links in this project are **relative** (`traditional/`, `../images/`), so they work on both `yoursite.netlify.app` and `username.github.io/repo-name/` without changes.

---

## Before you go live

1. Add image files under `images/` (see blog cards and work pages for expected filenames).
2. Test locally: open `index.html` in a browser, or run a simple static server:
   ```bash
   npx serve .
   ```
3. Do not commit secrets (there are none required for this site).

---

## Which is better?

| | **Netlify** | **GitHub Pages** |
|---|-------------|------------------|
| Easiest custom domain | Yes | Yes (with DNS setup) |
| Redirects / legacy URLs | `netlify.toml` (included) | Needs extra config or HTML redirects |
| Deploy previews on PRs | Yes | Limited |
| Best if repo is on GitHub only | Still fine (connect repo) | Very simple |
| Analytics / forms | Built-in options | Bring your own |

**Recommendation:** Use **Netlify** if you want the smoothest deploy, redirects for old links, and a custom domain. Use **GitHub Pages** if you prefer everything in one GitHub repo and a project URL like `username.github.io/portfolio` is enough.

Both are free for a personal portfolio at this scale.
