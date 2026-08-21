# tabletofarmslo.org

Landing page for **Table to Farm SLO** — a Zero Foodprint program from SLO Climate Coalition.

Static site, no build step: `index.html` + `assets/`.

## How it's served

- **Staging:** GitHub Pages serves this repo at `https://epearse.github.io/tabletofarmslo/` — anyone with the link can view it. The live domain is not affected.
- **Production (when ready):** connect this repo to **Cloudflare Pages** (Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git → pick this repo; framework preset "None", build command empty, output directory `/`). Then add the custom domain `www.tabletofarmslo.org` (and `tabletofarmslo.org`) in the Pages project's Custom domains tab — Cloudflare updates DNS for you, replacing the current redirect to the SLOCC page. Every later `git push` to `main` deploys automatically.

## Editing

- Colors and fonts are CSS variables at the top of `index.html` (`--forest`, `--gold`, `--cream`, …) following the Table to Farm brand brief (earthy palette sampled from the badge; Lora + Poppins).
- Stats ($9.5M+, 825+ grants, 240,000 t CO2) live in the dark stat-band section — update them there as Zero Foodprint publishes new numbers.
- If the site is ever rebuilt in React/Vite, Cloudflare Pages handles the build automatically — set the framework preset accordingly.
