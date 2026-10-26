# boschrosa.com

Source for www.boschrosa.com. Plain HTML and CSS: no build step, no JavaScript, and no requests to third parties (the fonts are self-hosted, so no Google Fonts and no cookies).

The paper PDFs are not stored here. They stay in `CirilBR/PaperRepository`, served at `papers.boschrosa.com`.

| File | What it is |
|---|---|
| `index.html` | All page content |
| `style.css` | Design, light and dark themes, print layout |
| `fonts/` | Newsreader and Archivo, subset to Latin (SIL Open Font License, texts included) |
| `photo.jpg` | Square portrait, shown at up to 240 × 240 px. Keep the file at least 800 × 800 px |
| `CNAME` | Tells GitHub Pages to serve the site at www.boschrosa.com |
| `404.html`, `favicon.svg` | Not-found page and browser-tab icon |

## Adding or moving a paper

Copy an existing `<li class="paper">…</li>` block in `index.html` and edit it. Then update the count in two places (the row of section links near the top and the section heading) and the "Last updated" line in the footer.

In the publications list, the year sits in the left margin and is shown once per year. For a second paper in the same year, write the year as `<span class="mark"><span class="sr">2024</span></span>` so screen readers still hear it.

## Hosting

The site is served by GitHub Pages from the `main` branch of this repository (folder `/`). Pushing to `main` publishes changes within a minute or two. The repository is public because GitHub Free only runs Pages from public repositories.

DNS for boschrosa.com is managed at Squarespace Domains (formerly Google Domains). The records that matter:

| Name | Type | Value | Purpose |
|---|---|---|---|
| `www` | CNAME | `cirilbr.github.io` | This site |
| `@` | A | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` | Bare boschrosa.com; GitHub redirects it to www |
| `papers` | CNAME | `cirilbr.github.io` | The PDFs, from `CirilBR/PaperRepository` |
| `_github-pages-challenge-cirilbr` | TXT | (verification code) | Proves to GitHub that you own the domain. Keep it. |

boschrosa.com is a verified domain in your GitHub account (Settings → Pages), so nobody else can claim its subdomains on GitHub. "Enforce HTTPS" is on for `papers.boschrosa.com` and should be on for this site too (Settings → Pages).

The old Google Site no longer receives traffic. You can remove its custom domain in Google Sites (Settings → Custom domains) or delete it.
