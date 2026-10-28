# op-landing

Public marketing site for **Operator Pages** — operatorpages.com

**Stack:** static HTML (no build step)  
**Host:** Cloudflare Pages  
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

## Deploy (Cloudflare Pages)

1. Cloudflare Dashboard → Pages → Create project → Connect Git
2. Select `danpennic-sys/op-landing` (grant access if private)
3. Build settings:
   - Framework preset: **None**
   - Build command: *(empty)*
   - Build output directory: `/` (root)
4. Save and deploy
5. Custom domain: add `operatorpages.com` and follow DNS instructions (CNAME to Pages)

Production URL and DNS remain **unverified** until you complete steps 4–5 in your Cloudflare account.

## Local preview

```bash
# any static server
python3 -m http.server 8080
# open http://127.0.0.1:8080
```

## Discipline

Claims lag the product. No PQC claims until shipped with conformance vectors.
