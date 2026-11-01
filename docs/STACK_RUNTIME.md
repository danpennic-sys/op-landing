# Operator Pages — stack runtime standard

**Synced 2026-11-01.** Use these floors on new work and when bumping older repos.

| Runtime | Standard | Notes |
|---------|----------|--------|
| **Node.js** | **26** (Active LTS) | `.nvmrc` = `26`; `engines.node: ">=26"` |
| **Go** | **1.26** | `go.mod` + `actions/setup-go@v5` |
| **Python** | **3.12+** (CI: 3.12 and 3.13) | Prefer 3.12 slim images |
| **Rust** | edition **2021**; MSRV ≥ **1.85** when declared | No forced edition 2024 without tests |
| **Actions** | `checkout@v4`, `setup-node@v4`, `setup-go@v5`, `setup-python@v5` | Avoid EOL major actions |

## Synced this pass

| Repo | Change |
|------|--------|
| `operatorpagesllc` | Node 26, Go 1.26, Python 3.12 |
| `quantumguard` | Go 1.26 |
| `quantumguard-operator` | release CI Go 1.26 |
| `binderseal` | CI Python 3.12 / 3.13 |
| `operator-app` | Node ≥26 + CI |
| `operator-desk-workstation` | Go 1.26 |
| `operator-pages-tools` | publish Python 3.12 |
| `FORCE` | engines ≥26, `.nvmrc`, CI |
| `quietpan` | rust-version 1.85 |

## No runtime pins (nothing to bump)

Python single-file CLIs without Docker/CI: `mediaseal`, `veriquote`, `jobseal`, `fieldseal`, `ledgerlite`, `safetyseal`, `changeorderseal`, `punchlistseal`, `closeseal`, `lifecycleseal`, `voiceseal`.

Static/HTML only: `op-landing` (except this doc), `operatorpages`, `packgate`, etc.

Rust with edition 2021 + stable CI already: `openrouter_free`, `chaser`, `evidence-core`, `podcastforge`.

## Not a repo

- `operator-sdk` does not exist under `danpennic-sys`.

## Rule

Do not introduce Node ≤20, Go ≤1.22, or Python ≤3.10 in new Dockerfiles or workflows.
