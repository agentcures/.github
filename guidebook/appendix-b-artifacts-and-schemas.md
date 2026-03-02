# Appendix B: Artifacts and Schemas

This appendix provides practical schema patterns and artifact templates for implementation and review workflows.

## B.1 Plan Contract (Minimal)

```json
{
  "calls": [
    {
      "tool": "refua_validate_spec",
      "args": {
        "action": "fold",
        "entities": [
          {
            "type": "protein",
            "id": "A",
            "sequence": "MKTAYIAKQRQISFVKSHFSRQLEERLGLIEVQ"
          },
          {
            "type": "ligand",
            "id": "lig",
            "smiles": "CCO"
          }
        ]
      }
    }
  ]
}
```

## B.2 Plan Quality Rules

Recommended rules:

1. top-level key `calls` must exist and be an array
2. every call must include `tool` and `args`
3. every tool must be in an allowlist
4. expensive calls should be preceded by validation when applicable
5. no free-form shell text should appear in plan payload

## B.3 Example Fold Call

```json
{
  "tool": "refua_fold",
  "args": {
    "name": "protein_ligand_demo",
    "entities": [
      {
        "type": "protein",
        "id": "A",
        "sequence": "MKTAYIAKQRQISFVKSHFSRQLEERLGLIEVQ"
      },
      {
        "type": "ligand",
        "id": "lig",
        "smiles": "CCO"
      }
    ],
    "affinity": {"binder": "lig"},
    "admet": true
  }
}
```

## B.4 Campaign Artifact Shape (Suggested)

```json
{
  "objective": "string",
  "plan": {"calls": []},
  "tool_results": [],
  "promising_cures": [],
  "policy_trace": [],
  "warnings": [],
  "provenance": {}
}
```

Suggested required fields:

- objective
- plan
- executed tool result list
- provenance metadata
- timestamp and run identifier

## B.5 Evidence Bundle Layout

```text
bundle/
  manifest.json
  decisions.jsonl
  lineage.json
  checksums.sha256
  artifacts/
  checklists/
```

## B.6 Decision Record Template

Use `decisions.jsonl` entries with fields such as:

- `decision_id`
- `objective`
- `decision_text`
- `input_artifacts`
- `output_artifacts`
- `data_provenance_refs`
- `model_provenance_refs`
- `gate_status`
- `review_owner`
- `timestamp_utc`

## B.7 Traceability Matrix Pattern

Tabular fields that improve review clarity:

| Field | Purpose |
| --- | --- |
| decision_id | stable cross-reference key |
| objective | decision context |
| tool_or_process | execution provenance shortcut |
| input_refs | upstream evidence links |
| output_refs | resulting artifact links |
| benchmark_gate | performance quality state |
| checklist_gate | compliance/readiness state |
| final_status | proceed/hold/rework decision |

## B.8 CI Validation Heuristics

Automate these checks:

1. plan/tool JSON schema validation
2. required provenance field presence
3. checksum verification for evidence bundles
4. benchmark gate status check before promotion
5. checklist unresolved-item policy enforcement

## B.9 Included Reference Files

- [tool_calls_example.json](./data/tool_calls_example.json)
- [campaign_lifecycle_example.csv](./data/campaign_lifecycle_example.csv)
- [traceability_matrix.csv](./data/traceability_matrix.csv)
- [medchem_property_guide.csv](./data/medchem_property_guide.csv)
- [development_stage_gates.csv](./data/development_stage_gates.csv)

## B.10 Practical Review Bundle Checklist

Before final stage-gate review:

- run compare/gating outputs are attached
- evidence checksums verify successfully
- all manual-review checklist items have owners
- unresolved risks are explicit in decision packet
- next action (proceed/hold/rework) is documented with rationale

