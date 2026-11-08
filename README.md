# hypnotoadie.github.io

Personal site and blog for Aaron Cochran, built with [Quarto](https://quarto.org) and published to GitHub Pages.

## Go live (one-time setup)

1. **Create the repo** on GitHub named exactly `hypnotoadie.github.io` (public, no README).
2. **Push this folder:**
   ```bash
   git init -b main
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/hypnotoadie/hypnotoadie.github.io.git
   git push -u origin main
   ```
3. **Create the `gh-pages` branch once**, from your machine:
   ```bash
   quarto publish gh-pages
   ```
4. **Point Pages at it:** repo → Settings → Pages → Source: *Deploy from a branch* → Branch: `gh-pages` / `(root)`.
5. Visit <https://hypnotoadie.github.io>. From now on, every push to `main` rebuilds the site through `.github/workflows/publish.yml`.

## Write a post

1. Copy `posts/_post-template.qmd` to `posts/<short-slug>/index.qmd`.
2. Fill in `title`, `description`, `date`, and **one primary track first** in `categories`:
   `Technical`, `Gov data` or `Off the clock`. The landing page shows the first one.
3. Preview with `quarto preview`, delete the `draft: true` line, then commit and push.

Posts with R or Python code are frozen (`freeze: true`): render locally, then commit the `_freeze/` folder so CI doesn't need R.

## Where things live

| File | What it controls |
|---|---|
| `_quarto.yml` | Navbar, footer, site URL, dark/light themes |
| `index.qmd` | Landing page (hero, work cards, recent posts, about band, sign-off) |
| `_recent-posts.ejs` | Layout of the "Writing" list on the landing page |
| `blog.qmd` | Full post listing with category filters + RSS feed (`blog.xml`) |
| `about.qmd`, `contact.qmd` | About and contact pages |
| `styles/dark.scss` | Dark palette (default) |
| `styles/light.scss` | Light palette (navbar toggle) |
| `styles/site.scss` | Shared layout and component styles |
| `assets/contact.html` | Click-to-reveal email script (keeps the address out of page source) |
