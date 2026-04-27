<div align="center">

# AgentCures

**Agentic software for end-to-end drug discovery execution**

<a href="https://www.agentcures.com"><img alt="Website" src="https://img.shields.io/badge/website-agentcures.com-0A0A0A?style=for-the-badge"></a>
<a href="https://github.com/agentcures"><img alt="GitHub Organization" src="https://img.shields.io/badge/github-agentcures-1F6FEB?style=for-the-badge"></a>
<a href="https://github.com/agentcures?tab=repositories"><img alt="Repositories" src="https://img.shields.io/badge/repos-15-238636?style=for-the-badge"></a>
<a href="https://github.com/agentcures/refua"><img alt="Core Toolkit" src="https://img.shields.io/badge/core-refua-BD561D?style=for-the-badge"></a>

</div>

AgentCures builds an integrated stack for planning, simulation, model inference, execution, evidence generation, and deployment in drug discovery programs.

## Guidebook

[Click to read the Guidebook](https://github.com/agentcures/.github/tree/main/guidebook)

## Platform Topology

```mermaid
flowchart TD
    S[clawcures-ui] --> C[ClawCures]
    C --> M[refua-mcp]
    M --> R[refua]
    R --> N[refua-notebook]
    C --> D[refua-data]
    C --> P[refua-preclinical]
    C --> W[refua-wetlab]
    C --> L[refua-clinical]
    C --> H[refua-schema]
    C --> G[refua-regulatory]
    C --> B[refua-bench]
    S --> G
    S --> L
    S --> P
    S --> D
    X[refua-deploy] --> S
    X --> C
    X --> M
```

## Repository Map

| Repository | Purpose | Key Features |
| --- | --- | --- |
| [`agentcures/ClawCures`](https://github.com/agentcures/ClawCures) | Drug disovery agent (OpenClaw based) | OpenClaw planning, autonomous loops, policy checks, portfolio ranking |
| [`agentcures/NanoCures`](https://github.com/agentcures/NanoCures) | Drug discovery agent (NanoClaw based) | Container-isolated execution, per-group sessions, sender allowlists, translational workflow skills |
| [`agentcures/refua`](https://github.com/agentcures/refua) | Core drug discovery ML toolkit | Boltz2 fold/affinity, BoltzGen design, unified Python API |
| [`agentcures/refua-mcp`](https://github.com/agentcures/refua-mcp) | Typed MCP server for Refua tools | Structured tool contracts, fold/design/affinity, optional clinical and preclinical extras |
| [`agentcures/clawcures-ui`](https://github.com/agentcures/clawcures-ui) | Web control plane | Mission planning, job telemetry, trial and evidence workflows |
| [`agentcures/refua-data`](https://github.com/agentcures/refua-data) | Data layer | Curated catalogs, API ingestion, local caching, parquet materialization |
| [`agentcures/refua-preclinical`](https://github.com/agentcures/refua-preclinical) | Preclinical operations | GLP study planning, in vivo scheduling, bioanalysis pipelines |
| [`agentcures/refua-wetlab`](https://github.com/agentcures/refua-wetlab) | Wet lab operations | Experiment orchestration, assay tracking, sample lifecycle coordination |
| [`agentcures/refua-clinical`](https://github.com/agentcures/refua-clinical) | Clinical simulation | PK/PD virtual patients, adaptive trial simulation, protocol optimization |
| [`agentcures/refua-schema`](https://github.com/agentcures/refua-schema) | Portfolio object model | `Portfolio -> Disease -> Rationale -> Drug` hierarchy, reused Refua objects, JSON/YAML round-tripping |
| [`agentcures/refua-regulatory`](https://github.com/agentcures/refua-regulatory) | Regulatory evidence and audit | Decision lineage, signed bundles, checklist gates |
| [`agentcures/refua-bench`](https://github.com/agentcures/refua-bench) | Benchmarking and regression gates | Statistical comparisons, provenance capture, baseline promotion |
| [`agentcures/refua-notebook`](https://github.com/agentcures/refua-notebook) | Notebook visualization layer | Rich IPython and Jupyter rendering for Refua objects |
| [`agentcures/refua-deploy`](https://github.com/agentcures/refua-deploy) | Deployment generation | Kubernetes/Compose/single-machine bundles for cloud and on-prem |

## Live Repository Cards

| Repository | Live Snapshot |
| --- | --- |
| [`agentcures/refua`](https://github.com/agentcures/refua) | ![Stars](https://img.shields.io/github/stars/agentcures/refua?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua?style=flat-square) |
| [`agentcures/ClawCures`](https://github.com/agentcures/ClawCures) | ![Stars](https://img.shields.io/github/stars/agentcures/ClawCures?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/ClawCures?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/ClawCures?style=flat-square) |
| [`agentcures/NanoCures`](https://github.com/agentcures/NanoCures) | ![Stars](https://img.shields.io/github/stars/agentcures/NanoCures?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/NanoCures?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/NanoCures?style=flat-square) |
| [`agentcures/refua-mcp`](https://github.com/agentcures/refua-mcp) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-mcp?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-mcp?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-mcp?style=flat-square) |
| [`agentcures/clawcures-ui`](https://github.com/agentcures/clawcures-ui) | ![Stars](https://img.shields.io/github/stars/agentcures/clawcures-ui?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/clawcures-ui?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/clawcures-ui?style=flat-square) |
| [`agentcures/refua-data`](https://github.com/agentcures/refua-data) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-data?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-data?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-data?style=flat-square) |
| [`agentcures/refua-preclinical`](https://github.com/agentcures/refua-preclinical) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-preclinical?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-preclinical?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-preclinical?style=flat-square) |
| [`agentcures/refua-wetlab`](https://github.com/agentcures/refua-wetlab) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-wetlab?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-wetlab?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-wetlab?style=flat-square) |
| [`agentcures/refua-clinical`](https://github.com/agentcures/refua-clinical) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-clinical?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-clinical?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-clinical?style=flat-square) |
| [`agentcures/refua-schema`](https://github.com/agentcures/refua-schema) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-schema?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-schema?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-schema?style=flat-square) |
| [`agentcures/refua-regulatory`](https://github.com/agentcures/refua-regulatory) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-regulatory?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-regulatory?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-regulatory?style=flat-square) |
| [`agentcures/refua-bench`](https://github.com/agentcures/refua-bench) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-bench?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-bench?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-bench?style=flat-square) |
| [`agentcures/refua-notebook`](https://github.com/agentcures/refua-notebook) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-notebook?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-notebook?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-notebook?style=flat-square) |
| [`agentcures/refua-deploy`](https://github.com/agentcures/refua-deploy) | ![Stars](https://img.shields.io/github/stars/agentcures/refua-deploy?style=flat-square&logo=github) ![Last Commit](https://img.shields.io/github/last-commit/agentcures/refua-deploy?style=flat-square) ![Open Issues](https://img.shields.io/github/issues/agentcures/refua-deploy?style=flat-square) |

## End-to-End Program Flow

1. Define mission intent in `clawcures-ui` or `ClawCures`.
2. Build candidate evidence and portfolio objects through `refua`, `refua-mcp`, `refua-data`, and `refua-schema`.
3. Simulate wet lab, preclinical, and clinical strategy with `refua-wetlab`, `refua-preclinical`, and `refua-clinical`.
4. Gate quality with `refua-bench`.
5. Package traceable evidence with `refua-regulatory`.
6. Render and apply runtime bundles with `refua-deploy`.

## External Links

- Website: https://www.agentcures.com
- News: https://www.agentcures.com/news
