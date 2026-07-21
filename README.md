# metpo-attic

Archived code removed from [berkeleybop/metpo](https://github.com/berkeleybop/metpo) during scope-narrowing. Nothing here is maintained. It is kept only so retired work stays recoverable and readable without digging through git history.

## Contents

### `presentations/`

The nine one-shot Python scripts that generated figures and analysis for the ICBO 2025 METPO talk. They previously lived at `metpo/presentations/` in the ontology repo. They are not part of the ontology build, the released artifacts, or the production CLI, and were never maintained as reusable tools.

| Script | What it did |
|--------|-------------|
| `analyze_bactotraits.py` | BactoTraits dataset analysis |
| `analyze_kg_microbe_metpo.py` | METPO usage across KG-Microbe datasets |
| `analyze_madin_etal.py` | Madin et al. dataset analysis |
| `analyze_ontogpt_grounding.py` | OntoGPT grounding quality |
| `analyze_ontology_landscape.py` | Related-ontology comparison |
| `analyze_primary_sources.py` | Primary-source comparison |
| `analyze_sssom_mappings.py` | SSSOM mapping analysis |
| `calculate_minimum_import_set.py` | Minimal import-closure computation |
| `generate_feedback_loop.py` | Feedback generation for term improvements |

### `tests/`

`test_analyze_ontogpt_grounding.py` was the only test covering a presentations script. It is archived here alongside the code it exercised; it was removed from metpo in the same change.

## Provenance

- Source repo: [berkeleybop/metpo](https://github.com/berkeleybop/metpo)
- Original path: `metpo/presentations/`
- Removed by: [berkeleybop/metpo#456](https://github.com/berkeleybop/metpo/pull/456) (umbrella [#433](https://github.com/berkeleybop/metpo/issues/433))
- Removed from metpo `main` at commit `9ef3859`
- Last substantive change to these scripts: metpo commit `9dbf53e` (2026-06-02)

To recover a file with its full metpo history instead of this snapshot:

```bash
git -C <metpo-clone> log --all -- metpo/presentations/<file>.py
```
