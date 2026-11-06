# treantlabs.com

Static site for Treant Private Limited. Plain HTML/CSS, no build step.

- `index.html`: home page
- `privacy.html`: privacy policy (link this URL in App Store / Play Console listings: https://treantlabs.com/privacy.html)
- `assets/`: stylesheet and logo
- `CNAME`: custom domain for GitHub Pages

## Preview locally

    python3 -m http.server 8000

Then open http://localhost:8000.

## Deploy on GitHub Pages

1. Push this folder to a GitHub repo (e.g. `treantlabs/treantlabs.com`) on the `main` branch.
2. Repo → Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)`.
3. Custom domain: `treantlabs.com` (already set by the `CNAME` file). Tick **Enforce HTTPS** once the certificate is issued.
4. DNS at your domain registrar:
   - Apex `treantlabs.com`: four `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
     (optional `AAAA`: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`)
   - `www`: `CNAME` → `<your-github-username>.github.io`
5. Optional but recommended: verify the domain under your GitHub account/org settings → Pages, to stop anyone else claiming it.

Any push to `main` redeploys automatically.
