# docs.nygen.io

The landing page for [docs.nygen.io](https://docs.nygen.io/). This repository is the organization's GitHub Pages site, so it owns the domain root. Every other repository that publishes GitHub Pages is served under it at `docs.nygen.io/<RepoName>/`. Example: [CyteArc](https://docs.nygen.io/CyteArc/).

Plain static files deployed from `master`, no build step.

| File | Purpose |
| :-- | :-- |
| `index.html` | Hub page with one card per project |
| `404.html` | Not-found page. Also fixes the case of project paths (`/cytearc/...` → `/CyteArc/...`) |
| `robots.txt` | Crawl rules and one `Sitemap:` line per project. Only the root copy counts, so project builds must not write their own. |
| `sitemap.xml` | Sitemap for this page. Project sitemaps are listed in `robots.txt`. |
| `llms.txt` | Plain-text index for language models, linking each project's own `llms.txt` or docs |

## Adding a project

1. In the project repo, deploy GitHub Pages without a custom domain. Build with base path `/<RepoName>` and upload the HTML at the artifact root.
2. Here, add a card to `index.html` (and its `SoftwareSourceCode` entry in the JSON-LD), a line to `llms.txt`, a `Sitemap:` line to `robots.txt`, and an entry in the `projects` map in `404.html`.
