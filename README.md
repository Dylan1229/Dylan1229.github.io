# home.fanjiang.net

Personal academic homepage for **Fanjiang Ye (叶繁江)** — Ph.D. student in Computer Science at Rice University.

Live at: <https://home.fanjiang.net/>

## Structure

This is a single-file static page. `index.html` is self-contained (only external
dependency is Google Fonts) with a handful of local image and PDF assets. No
build step, no package manager, no server.

- `index.html` — the homepage (HTML + inline CSS + a tiny inline script for the theme toggle)
- `images/` — avatar and personal hobby photos
- `pdfs/` — CV
- `.nojekyll` — tells GitHub Pages to serve files as-is (skip Jekyll processing)
- `favicon.ico`, `CNAME`, `LICENSE` — standard metadata

The previous Jekyll-based version of this site is preserved on the
[`jekyll-archive`](https://github.com/Dylan1229/Dylan1229.github.io/tree/jekyll-archive)
branch if you need it for historical reference. It's not on `master` so that
anyone using this repo as a template gets a clean working tree.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Or just double-click `index.html` to open it with a `file://` URL.

---

## Use this as a template

Feel free to fork or clone this repo as a starting point for your own academic
homepage. The entire site is ~1000 lines of HTML + CSS in a single file — no
framework, no package manager, no build step.

### Quick start

```bash
# 1. Clone (or fork on GitHub first, then clone your fork)
git clone https://github.com/Dylan1229/Dylan1229.github.io.git my-homepage
cd my-homepage

# 2. Remove my git history and start your own
rm -rf .git
git init
git add .
git commit -m "Initial commit from Dylan1229/Dylan1229.github.io template"

# 3. Point at your own GitHub repo (name it <your-username>.github.io)
git remote add origin git@github.com:<YOUR_USERNAME>/<YOUR_USERNAME>.github.io.git
git push -u origin master
```

### What to change in `index.html`

| Where | What to update |
|---|---|
| `<title>`, `<meta name="description">`, `<meta name="author">` | Your name + one-line description |
| `<h1 class="display-name">` | Your name. The `<span class="cjk">` is a CJK name rendered in a signature-style font (`Zhi Mang Xing`). Delete it, replace with your own script, or keep it empty. |
| `<p class="role-line">` | Role · field · institution tag line |
| `<div class="bio-prose">` | Your bio paragraph with links to advisor, university, etc. |
| `<aside class="callout">` | Job-market / collaboration invitation — or delete the whole `<aside>` block |
| `<ul class="links">` | Contact icons. Update each `href` and `aria-label`. GitHub / LinkedIn / Google Scholar SVGs are from [Simple Icons](https://simpleicons.org/). Email and CV use hand-written generic SVGs — you can leave them or swap for anything else. |
| `#research-interests` | Your research summary |
| `#publications` | Publication list, split into two groups: a top-level `<ol>` of always-visible published papers, and a `<details>` block of collapsed preprints. Each `<li class="entry">` has `.entry-meta` (venue label, mono) + `.entry-body` with `.entry-title` / `.entry-authors` / `.entry-links`. Add `class="entry highlight"` to render the venue label in accent color (for spotlight / best paper). Wrap your own name in `<span class="me">` for the bold-underline self-highlight. |
| `#education`, `#experience` | Each entry = mono date on the left, 3 lines on the right: `.record-line.primary` (institution), `.secondary` (role / degree), `.tertiary` (advisor or location) |
| `#services` → `<h3>` subsections | Service-type subheadings + flat bullet lists |
| `#teaching` | Course list |
| `#miscellaneous` | Anything personal — hobbies, links to photos |
| `.news-panel` → `.news-panel-body` | Right-side news feed. Each `.news-item` has `.news-date` (mono) + `.news-text`. Hidden below 1200px viewport width by default. |
| `.colophon` footer | Last-updated date and the "steal this website's source code" line — **point the link to your own fork**, not mine |

### What to replace in the repo

1. **`CNAME`** — replace with your own custom domain, or delete entirely if you use `<username>.github.io` directly
2. **`images/`** — replace with your own assets. Current contents: `Fanjiang.png` (avatar) + a few hobby photos referenced from `#miscellaneous`. Update `<img src>` and `<a href>` references in `index.html` accordingly.
3. **`pdfs/CV_FanjiangYe.pdf`** — replace with your CV. Update the link in `<ul class="links">`.
4. **`favicon.ico`** — replace with your own

### Reskin without restructuring

Just tweak the CSS custom properties in `:root` (and `[data-theme="dark"]` for
dark mode) near the top of `<style>`:

- `--bg`, `--bg-raised`, `--ink`, `--ink-muted`, `--ink-faint`, `--rule` — warm cream palette
- `--accent`, `--accent-warm` — single accent color for links and highlights
- `--font-display`, `--font-body`, `--font-mono` — typography stacks. If you swap the font families, also update the Google Fonts `<link>` at the top of `<head>`.
- `--fs-display`, `--fs-h2`, `--fs-body`, `--fs-meta` — size scale

### Deploy on GitHub Pages

1. Name your repo `<username>.github.io`
2. Push to `master` (or `main`)
3. In repo **Settings → Pages**, verify the source branch matches
4. Wait 1–2 minutes, visit `https://<username>.github.io/`
5. For a custom domain, edit `CNAME` and add DNS records per the [GitHub Pages docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

The `.nojekyll` file at the root tells GitHub Pages to skip Jekyll processing
and serve files as-is. Don't delete it unless you specifically want Jekyll back.

### Regenerate from scratch with pageclaw

If you want a completely fresh design rather than adapting this one, the site
was originally generated by
[**pageclaw**](https://github.com/XY-Showing/pageclaw) — a skill-based pipeline
that turns a `page-story-*.md` brief into a polished static page through a
design-context → design-system → impl-plan → build → polish + audit workflow.
Install pageclaw as a skill in Claude Code / Codex / OpenCode, write a
`page-story-<yourname>.md` describing yourself, then `/page-claw page-story-<yourname>.md`.

---

## License

MIT — see [LICENSE](LICENSE). The license applies to the code; content (bio,
publications, news, photos) is personal and not part of the template.
