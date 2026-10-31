# op-landing

Public marketing site for **Operator Pages** — operatorpages.com

**Stack:** static HTML (no build step)  
**Hosts:** Cloudflare Pages (primary target) **and** GitHub Pages  
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

## Deploy — Cloudflare Pages (primary target)

Config: `wrangler.toml` (static, no build).

1. Cloudflare Dashboard → Pages → Create project → Connect to Git
2. Select `danpennic-sys/op-landing`
3. Build settings:
   - Framework preset: **None**
   - Build command: *(empty)*
   - Build output directory: `/` (root)
4. Save and deploy
5. Custom domain: `operatorpages.com` (or `www`)

**DNS and production deployment remain UNVERIFIED** until you complete the Cloudflare project + DNS records in your account.

Use **one** platform as the DNS apex for `operatorpages.com` to avoid conflicting CNAMEs.

| Role | Platform |
|------|----------|
| Primary custom domain | Cloudflare Pages |
| Backup / preview | GitHub Pages `*.github.io` |

---

## Deploy — GitHub Pages (backup)

Workflow: `.github/workflows/pages.yml` (runs on every push to `main`).

### One-time setup

1. Repo **Settings → Pages**
2. **Source:** GitHub Actions
3. (Optional) Custom domain only if Cloudflare is **not** the apex

---

## Local preview

```bash
python3 -m http.server 8080
# open http://127.0.0.1:8080
```

## Discipline

Claims lag the product. No PQC claims until shipped with conformance vectors.  
Stripe payment link must stay identical across every CTA.
