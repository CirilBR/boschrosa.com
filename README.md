# boschrosa.com

Source for www.boschrosa.com. Plain HTML and CSS: no build step, no JavaScript, and no requests to third parties (the fonts are self-hosted, so no Google Fonts and no cookies).

The paper PDFs are not stored here. They stay in `CirilBR/PaperRepository`, served at `papers.boschrosa.com`.

| File | What it is |
|---|---|
| `index.html` | All page content |
| `style.css` | Design, light and dark themes, print layout |
| `fonts/` | Newsreader and Archivo, subset to Latin (SIL Open Font License, texts included) |
| `photo.jpg` | Square portrait; its displayed size follows the name beside it. Keep the file at least 800 × 800 px |
| `CNAME` | Tells GitHub Pages to serve the site at www.boschrosa.com |
| `404.html`, `favicon.svg` | Not-found page and browser-tab icon |

## Adding or moving a paper

Copy an existing `<li class="paper">…</li>` block in `index.html` and edit it. Then update the count in two places (the sidebar list and the section heading) and the "Last updated" line in the footer.

In the publications list, the year sits in the left margin and is shown once per year. For a second paper in the same year, write the year as `<span class="mark"><span class="sr">2024</span></span>` so screen readers still hear it.

## Staying private until launch

The repository is private and GitHub Pages is switched off, so nothing here is reachable on the web. The old Google Site keeps serving www.boschrosa.com until the DNS change in step 5.

GitHub Pages sites are always public once switched on (access control exists only on GitHub Enterprise Cloud), so switching Pages on is the launch.

## Launch checklist

1. **HTTPS for the PDFs.** In `PaperRepository` → Settings → Pages, tick "Enforce HTTPS". Today https://papers.boschrosa.com redirects to plain http. Once HTTPS works, change the `http://papers.boschrosa.com` links in `index.html` to `https://`.
2. **Verify the domain** (skip if done already). GitHub → your profile Settings → Pages → Add a domain → `boschrosa.com`, then add the TXT record it shows at your DNS provider. This stops anyone else from claiming your subdomains on GitHub.
3. **Repository visibility.** On GitHub Free, Pages only works from public repositories: Settings → General → Change visibility → Public. On GitHub Pro the repository can stay private; the site is public either way.
4. **Switch Pages on.** Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`. The custom domain field should fill in as `www.boschrosa.com` from the `CNAME` file.
5. **Point DNS at GitHub** at your domain registrar:
   - `www` → CNAME → `cirilbr.github.io` (replacing the Google Sites record, usually `ghs.googlehosted.com`)
   - bare `boschrosa.com`, if you want it to work too → A records `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - leave the `papers` record as it is
6. **Wait and lock in HTTPS.** DNS changes can take up to 24 hours. Once Settings → Pages shows the domain check passing, tick "Enforce HTTPS".
7. **Retire the Google Site.** Remove the custom domain mapping in Google Sites (or unpublish it).
