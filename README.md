# fedorlushnikov.com

Personal site of Fedor Lushnikov: **https://fedorlushnikov.com**

- Code: `site/` (one `index.html`, images in `site/img/`, fonts in `site/fonts/`).
- Hosting: GitHub Pages. Every push to `main` that touches `site/` deploys automatically (workflow `.github/workflows/pages.yml`), live in about a minute.
- Domain: `site/CNAME`. DNS points to GitHub Pages.
- Contact form: sends to Fedor's Gmail through formsubmit.co (no server).

## Editing with Claude Code
1. `git clone` this repo, open it with `claude`.
2. Ask for the change, check `site/index.html` in the browser.
3. Commit and push to `main`: the site updates by itself.
