# Operator Pages — stack runtime standard

**Synced 2026-11-01.** Use these floors on new work and when bumping older repos.

| Runtime | Standard | Notes |
|---------|----------|--------|
| **Node.js** | **26** (Active LTS) | `.nvmrc` = `26`; `engines.node: ">=26"` |
| **Go** | **1.26** | `go.mod` + `actions/setup-go@v5` |
| **Python** | **3.12+** (CI: 3.12 and 3.13) | Prefer 3.12 slim images |
| **Rust** | edition **2021**; MSRV ≥ **1.85** when declared | No forced edition 2024 without tests |
| **Actions** | `checkout@v4`, `setup-node@v4`, `setup-go@v5`, `setup-python@v5` | Avoid EOL major actions |

## Shared SDK

- **`operator-sdk`** (`@op/sdk`) — https://github.com/danpennic-sys/operator-sdk  
  MCP propose→confirm→apply client, CONTRACT-v1 shape helpers, runtime constants. Node 26+.

## Synced runtimes

`operatorpagesllc`, `quantumguard`, `quantumguard-operator`, `binderseal`, `operator-app`, `operator-desk-workstation`, `operator-pages-tools`, `FORCE`, `quietpan`.

## Rule

Do not introduce Node ≤20, Go ≤1.22, or Python ≤3.10 in new Dockerfiles or workflows.
