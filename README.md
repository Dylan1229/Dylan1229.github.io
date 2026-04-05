# home.fanjiang.net

Personal academic homepage for **Fanjiang Ye (叶繁江)** — Ph.D. student in Computer Science at Rice University.

Live at: <https://home.fanjiang.net/>

## Structure

This is a single-file static page. `index.html` is self-contained (only external
dependencies are Google Fonts and a few image assets under `images/`). No build
step, no package manager, no server.

- `index.html` — the homepage
- `images/` — avatar, institution logos, publication figures
- `pdfs/` — CV and other documents
- `.nojekyll` — tells GitHub Pages to serve files as-is without Jekyll processing
- `_archive-jekyll/` — the previous Jekyll-based site, kept for history

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Or just double-click `index.html` to open it with a `file://` URL.

## How it was built

Generated from a `page-story-*.md` brief via
[**pageclaw**](https://github.com/XY-Showing/pageclaw) — a skill-based pipeline
that turns a structured markdown story into a polished static page (design
context → design system → implementation plan → build → polish + audit).

The design artifacts (design doc, impl plan, audit report) live outside this
repository alongside the original page-story source.

## License

MIT — see [LICENSE](LICENSE).
