# op-landing

Public marketing site for **Operator Pages** — operatorpages.com

**Stack:** static HTML (no build step)  
**Hosts:** GitHub Pages **and** Cloudflare Pages  
**Featured product:** QuantumGuard + Operator Pack ($490)  
**Stripe:** `https://buy.stripe.com/5kQaEYc9AewBaJleoN0ZW01` (do not change without updating all CTAs)

## Pages

| Path | Purpose |
|------|---------|
| `/` | Home + $490 CTA |
| `/products/` | Catalog |
| `/products/quantumguard.html` | QuantumGuard Operator Pack detail |
| `/docs/` | Public contract links + licensed doc notes |
| `/access.html` | Post-purchase access instructions |

Licensed binaries, runbooks, and LICENSE.json are **not** in this repo.

---

## Deploy — GitHub Pages (recommended primary)

Workflow: `.github/workflows/pages.yml` (runs on every push to `main`).

### One-time setup

1. Repo **Settings → Pages**
2. **Source:** GitHub Actions
3. (Optional) **Custom domain:** `operatorpages.com`
   - Add DNS records GitHub shows (usually `CNAME` → `danpennic-sys.github.io`)
   - Enable **Enforce HTTPS** after DNS propagates

### Visibility note

- **Public repo** → free public site at `https://danpennic-sys.github.io/op-landing/` (or custom domain)
- **Private repo** → GitHub Pages requires GitHub Pro/Team/Enterprise for private sites

If this marketing site should be world-readable, make the repo **public** (licensed Operator Pack stays in private `quantumguard-operator`).

After the first successful Actions run, the site URL appears under **Settings → Pages**.

---

## Deploy — Cloudflare Pages (optional mirror / CDN)

1. Cloudflare Dashboard → Pages → Create project → Connect Git
2. Select `danpennic-sys/op-landing`
3. Build settings:
   - Framework preset: **None**
   - Build command: *(empty)*
   - Build output directory: `/` (root)
4. Save and deploy
5. Custom domain: `operatorpages.com` (or a subdomain like `www`)

Use **one** platform as the DNS apex for `operatorpages.com` to avoid conflicting CNAMEs. Typical pattern:

| Role | Platform |
|------|----------|
| Primary custom domain | Cloudflare Pages *or* GitHub Pages |
| Backup / preview | The other host’s default `*.pages.dev` / `*.github.io` URL |

Production URL and DNS remain **unverified** until you finish Pages setup + DNS in your accounts.

---

## Local preview

```bash
python3 -m http.server 8080
# open http://127.0.0.1:8080
```

## Discipline

Claims lag the product. No PQC claims until shipped with conformance vectors.
