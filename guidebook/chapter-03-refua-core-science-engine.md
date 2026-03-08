# Chapter 3: Refua Core Science Engine

## Chapter Summary

This chapter introduces `refua` as the scientific inference core and shows how to use its object model to run fold, affinity, design, and property workflows in a reproducible way.
The emphasis is on interpreting outputs as decision-support signals within larger campaign loops.

## Learning Goals

By the end of this chapter, you should be able to:

Explain the Refua object model and workflow style. Choose between fold, affinity, and design-oriented paths. Interpret outputs in a decision-support context. Integrate Refua outputs into broader campaign loops.

## Story Thread

This chapter follows the moment when a hypothesis becomes an executable scientific run.
You define entities, run the workflow, and then face the harder question: what does this output actually mean for decisions?
The goal is not just running models, but turning outputs into reliable next actions.

## 3.1 What Refua Is

`refua` is the scientific inference core for this ecosystem.
It unifies:

Structure modeling workflows. Affinity-oriented evaluation paths. Generative binder design workflows. Property-level analysis for proteins and small molecules.

The design goal is to keep scientific workflows composable, typed, and in memory.

## 3.2 Core API Objects

| Object | Purpose | Typical Usage |
| --- | --- | --- |
| `Protein` | define sequence entities | targets, context proteins, property analysis |
| `SM` | define small molecules by SMILES | ligand modeling, descriptor/ADMET analysis |
| `Binder` | define binder templates or specs | peptide/macrocycle design scaffolding |
| `Complex` | assemble multi-entity system | unified entrypoint for fold/design/affinity workflows |
| `BinderDesigns` | provide high-level presets | antibody and peptide design setup |

## 3.3 Typical Workflow Shapes

### Shape A: Protein-Ligand Structural Evaluation

1. define target protein
2. define ligand SMILES
3. create complex
4. run fold with affinity request
5. inspect structure and affinity signals

### Shape B: Binder Design Loop

1. define target context
2. create binder placeholders or presets
3. run fold/design workflow
4. rank candidates by confidence and downstream filters

### Shape C: Property-Triage Loop

1. compute molecule/protein properties
2. apply early liability filters
3. route only promising candidates to expensive workflows

## 3.4 Execution Diagram

```mermaid
flowchart LR
    A[Entities and constraints] --> B[Validation and normalization]
    B --> C[Fold or affinity execution]
    C --> D[Result object]
    D --> E[Analysis and campaign ranking]
```

## 3.5 Why Unified API Matters

A unified API removes glue-code friction:

Fewer ad hoc file transforms. Fewer schema mismatch bugs. Easier iterative loops inside notebooks and services. Easier integration with `refua-mcp`.

This is a major practical advantage over fragmented scripts.

## 3.6 Output Interpretation Principles

Refua outputs are evidence signals, not standalone truth.

Treat them as inputs to multi-signal decision making.

Strong structural confidence does not guarantee clinical efficacy. Promising affinity signal does not erase ADMET risk. Property scores need context and trend analysis, not one-off thresholds.

## 3.7 Property Layers

Refua supports rapid property extraction for triage.

Molecule-oriented examples:

Molecular descriptors and optional model-based ADMET profile path.

Protein-oriented examples:

Length, isoelectric point, hydropathy-related descriptors and liability-oriented heuristic properties.

These help prioritize what to evaluate deeply next.

## 3.8 Constraint-Aware Modeling

Constraint support helps encode domain knowledge:

Pocket/contact constraints. Template-informed structure contexts. Binder specification patterns.

This is useful when naive unconstrained generation drifts away from biological plausibility.

## 3.9 Practical Inference Pattern

```python
from refua import Complex, Protein, SM

target = Protein("MSEQNNTEMTFQIQRIYTKDISFEAPNAPHVFQQLAGKYTPEEIRNVLSTLQKAD", ids="A")
ligand = SM("Cn1cnc2n(C)c(=O)n(C)c(=O)c12")
result = Complex([target, ligand], name="kras_demo").request_affinity().fold()
print(result.affinity.ic50)
```

The key idea is not syntax. The key idea is keeping an explicit and reproducible spec for each run.

## 3.10 Performance And Operational Considerations

Keep model instances alive for repeated evaluations where possible. Use async mode through MCP for long-running workloads. Avoid overusing exploratory runs in expensive compute environments. Capture run metadata at invocation time for later governance.

## 3.11 Common Mistakes

Treating single-run outputs as final ranking authority. Skipping spec validation before expensive runs. Mixing entity IDs inconsistently across chained calls. Failing to preserve intermediate artifacts that explain final decisions.

## 3.12 Refua In The Full Stack

`refua` is the engine.
`ClawCures` is the planner/orchestrator.
`refua-mcp` is the typed interface and execution guardrail.
`clawcures-ui` is the operational command center.

That division lets teams improve model science without destabilizing orchestration and governance layers.

## Key Takeaways

`refua` unifies structural, affinity, design, and property workflows under one API model. Composable, in-memory workflows reduce glue-code fragility. Output interpretation should always include uncertainty and downstream constraints. Constraint-aware specs help align model execution with biological context. Reproducibility depends on explicit run specs and artifact retention.

## Quick Review Questions

1. When would you choose affinity-only execution over full fold workflows?
2. What extra signals do you need before promoting a candidate from one run result?
3. How do constraints reduce biologically implausible outputs?
4. What metadata should always accompany a Refua run artifact?
5. Which part of your current Refua usage is least reproducible today?

## Mini Case Study

**Scenario:** A ligand shows strong predicted affinity in one run and is immediately promoted by a team under deadline pressure.

**Decision Move:** A second reviewer requires a full evidence bundle: structural confidence context, property/ADMET checks, and consistent run metadata.

**Result:** The candidate remains interesting but is downgraded to \"needs further validation\" rather than \"advance now,\" avoiding a premature handoff.

**Lesson:** Single high-scoring outputs are triage signals, not final decisions.

## 3.13 Chapter Checkpoint

You are ready for Chapter 4 if you can answer:

When would you run fold vs affinity-only? What additional signals do you need beyond one affinity output? How would you keep run specs reproducible in team workflows?

## 3.14 Continue Reading

Campaign orchestration and policy loops: [Chapter 4](./chapter-04-clawcures-campaign-orchestrator.md) and lifecycle integration across packages: [Chapter 5](./chapter-05-program-lifecycle-modules.md).
