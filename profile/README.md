<div align="center">

# AgentCures

**Agentic software for end-to-end drug discovery execution**

<a href="https://www.agentcures.com"><img alt="Website" src="https://img.shields.io/badge/website-agentcures.com-0A0A0A?style=for-the-badge"></a>
<a href="https://github.com/agentcures"><img alt="GitHub Organization" src="https://img.shields.io/badge/github-agentcures-1F6FEB?style=for-the-badge"></a>
<a href="https://github.com/agentcures?tab=repositories"><img alt="Repositories" src="https://img.shields.io/badge/repos-12-238636?style=for-the-badge"></a>
<a href="https://github.com/agentcures/refua"><img alt="Core Toolkit" src="https://img.shields.io/badge/core-refua-BD561D?style=for-the-badge"></a>

</div>

AgentCures builds an integrated stack for planning, simulation, model inference, execution, evidence generation, and deployment in drug discovery programs.

## Platform Topology

```mermaid
flowchart TD
    S[refua-studio] --> C[ClawCures]
    C --> M[refua-mcp]
    M --> R[refua]
    R --> N[refua-notebook]
    C --> D[refua-data]
    C --> P[refua-preclinical]
    C --> L[refua-clinical]
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
| [`agentcures/.github`](https://github.com/agentcures/.github) | Organization profile and shared defaults | Profile README, org-level metadata |
| [`agentcures/ClawCures`](https://github.com/agentcures/ClawCures) | Campaign orchestration agent | OpenClaw planning, autonomous loops, policy checks, portfolio ranking |
| [`agentcures/refua`](https://github.com/agentcures/refua) | Core drug discovery ML toolkit | Boltz2 fold/affinity, BoltzGen design, unified Python API |
| [`agentcures/refua-mcp`](https://github.com/agentcures/refua-mcp) | Typed MCP server for Refua tools | Structured tool contracts, fold/design/affinity, optional clinical and preclinical extras |
| [`agentcures/refua-studio`](https://github.com/agentcures/refua-studio) | Web control plane | Mission planning, job telemetry, trial and evidence workflows |
| [`agentcures/refua-data`](https://github.com/agentcures/refua-data) | Data layer | Curated catalogs, API ingestion, local caching, parquet materialization |
| [`agentcures/refua-preclinical`](https://github.com/agentcures/refua-preclinical) | Preclinical operations | GLP study planning, in vivo scheduling, bioanalysis pipelines |
| [`agentcures/refua-clinical`](https://github.com/agentcures/refua-clinical) | Clinical simulation | PK/PD virtual patients, adaptive trial simulation, protocol optimization |
| [`agentcures/refua-regulatory`](https://github.com/agentcures/refua-regulatory) | Regulatory evidence and audit | Decision lineage, signed bundles, checklist gates |
| [`agentcures/refua-bench`](https://github.com/agentcures/refua-bench) | Benchmarking and regression gates | Statistical comparisons, provenance capture, baseline promotion |
| [`agentcures/refua-notebook`](https://github.com/agentcures/refua-notebook) | Notebook visualization layer | Rich IPython and Jupyter rendering for Refua objects |
| [`agentcures/refua-deploy`](https://github.com/agentcures/refua-deploy) | Deployment generation | Kubernetes/Compose/single-machine bundles for cloud and on-prem |

## Live Repository Cards

| | |
| --- | --- |
| [![refua](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua&theme=transparent)](https://github.com/agentcures/refua) | [![ClawCures](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=ClawCures&theme=transparent)](https://github.com/agentcures/ClawCures) |
| [![refua-mcp](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-mcp&theme=transparent)](https://github.com/agentcures/refua-mcp) | [![refua-studio](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-studio&theme=transparent)](https://github.com/agentcures/refua-studio) |
| [![refua-data](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-data&theme=transparent)](https://github.com/agentcures/refua-data) | [![refua-preclinical](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-preclinical&theme=transparent)](https://github.com/agentcures/refua-preclinical) |
| [![refua-clinical](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-clinical&theme=transparent)](https://github.com/agentcures/refua-clinical) | [![refua-regulatory](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-regulatory&theme=transparent)](https://github.com/agentcures/refua-regulatory) |
| [![refua-bench](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-bench&theme=transparent)](https://github.com/agentcures/refua-bench) | [![refua-notebook](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-notebook&theme=transparent)](https://github.com/agentcures/refua-notebook) |
| [![refua-deploy](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=refua-deploy&theme=transparent)](https://github.com/agentcures/refua-deploy) | [![.github](https://github-readme-stats.vercel.app/api/pin/?username=agentcures&repo=.github&theme=transparent)](https://github.com/agentcures/.github) |

## End-to-End Program Flow

1. Define mission intent in `refua-studio` or `ClawCures`.
2. Build candidate evidence through `refua`, `refua-mcp`, and `refua-data`.
3. Simulate preclinical and clinical strategy with `refua-preclinical` and `refua-clinical`.
4. Gate quality with `refua-bench`.
5. Package traceable evidence with `refua-regulatory`.
6. Render and apply runtime bundles with `refua-deploy`.

## External Links

- Website: https://www.agentcures.com
- News: https://www.agentcures.com/news
