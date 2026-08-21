# tabletofarmslo.org

Landing page for **Table to Farm SLO** — a Zero Foodprint program from SLO Climate Coalition.

Static site, no build step: `index.html` + `assets/`.

## Deploying on GitHub Pages + Cloudflare

1. **Create the repo** (e.g. `tabletofarmslo`) and push these files to the `main` branch.
2. **Enable Pages:** repo → Settings → Pages → Source: "Deploy from a branch" → branch `main`, folder `/ (root)`. The `CNAME` file in this folder tells GitHub the site's custom domain (`www.tabletofarmslo.org`).
3. **Cloudflare DNS** (your domain is on Cloudflare):
   - `CNAME` record: name `www` → target `<your-github-username>.github.io`. Start with Proxy status **DNS only** (grey cloud) until the certificate is issued; you can turn the orange cloud on afterwards.
   - Apex/root redirect: add `A` records for `tabletofarmslo.org` pointing to GitHub Pages IPs (`185.199.108.153`, `.109.153`, `.110.153`, `.111.153`), or use a Cloudflare redirect rule from `tabletofarmslo.org/*` to `https://www.tabletofarmslo.org/$1`.
4. **HTTPS:** back in GitHub → Settings → Pages, wait for the DNS check to pass, then tick **Enforce HTTPS**.
5. In Cloudflare, set SSL/TLS mode to **Full** (not Flexible) to avoid redirect loops when the orange cloud is on.

Changes pushed to `main` go live in a minute or two.

## Editing

- Colors and fonts are defined as CSS variables at the top of `index.html` (`--forest`, `--gold`, `--cream`, …) — they follow the Table to Farm brand brief (earthy palette sampled from the badge; Lora + Poppins).
- Stats ($9.5M+, 825+ grants, 240,000 t CO₂) live in the dark "stat band" section — update them there as Zero Foodprint publishes new numbers.
