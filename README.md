# boschrosa.com

Source for www.boschrosa.com. Plain HTML and CSS: no build step, no JavaScript, and no requests to third parties (the fonts are self-hosted, so no Google Fonts and no cookies).

The paper PDFs are not stored here. They stay in `CirilBR/PaperRepository`, served at `papers.boschrosa.com`.

| File | What it is |
|---|---|
| `index.html` | All page content |
| `style.css` | Design: same look as the old Google Site (Lato, three columns), one column on phones |
| `fonts/` | Lato, subset to Latin and self-hosted (SIL Open Font License, text included) |
| `photo.jpg` | Portrait, 600 × 797 px |
| `CNAME` | Tells GitHub Pages to serve the site at www.boschrosa.com |
| `404.html`, `favicon.svg` | Not-found page and browser-tab icon |

## Adding or moving a paper

Copy an existing `<li>…</li>` line in `index.html` and edit it. Paper titles are `<a class="t" href="…">`, journal names are `<span class="j">…</span>`, and the red labels are `<span class="flag">New !!</span>`.

"Sleeping Dogs Lying" is a fold-out section (`<details class="fold">`): its papers stay hidden until a visitor clicks the heading or the dog.

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
