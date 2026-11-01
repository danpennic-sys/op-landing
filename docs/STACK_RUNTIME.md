# Operator Pages — stack runtime standard

**Synced 2026-11-01.** Use these floors on new work and when bumping older repos.

| Runtime | Standard | Notes |
|---------|----------|--------|
| **Node.js** | **26** (Active LTS) | `.nvmrc` = `26`; `engines.node: ">=26"` |
| **Go** | **1.26** | `go.mod` + `actions/setup-go@v5` |
| **Python** | **3.12+** (CI: 3.12 and 3.13) | Prefer 3.12 slim images |
| **Rust** | edition **2021** (or newer when adopted) | No forced MSRV bump without tests |
| **Actions** | `checkout@v4`, `setup-node@v4`, `setup-go@v5`, `setup-python@v5` | Avoid EOL major actions |

## Already synced

- `operatorpagesllc` — Node 26, Go 1.26, Python 3.12
- `quantumguard` — Go 1.26
- `binderseal` — Python 3.12 / 3.13 CI
- `operator-app` — Node 26 + CI
- `operator-desk-workstation` — Go 1.26

## Not a repo

- `operator-sdk` does not exist under `danpennic-sys`. Create it only if you want a shared client SDK; pin to this table from day one.

## Rule

Do not introduce Node 18/20, Go ≤1.22, or Python ≤3.10 in new Dockerfiles or workflows.
