# metpo-attic

Archived code and content removed from [berkeleybop/metpo](https://github.com/berkeleybop/metpo) during scope-narrowing (umbrella [berkeleybop/metpo#433](https://github.com/berkeleybop/metpo/issues/433)). Nothing here is maintained. It is kept only so retired work stays recoverable and readable without digging through git history.

Each top-level directory is one retired subsystem, with its own provenance below.

## `presentations/` + `tests/`

The nine one-shot Python scripts that generated figures and analysis for the ICBO 2025 METPO talk, plus the single test that covered one of them. They previously lived at `metpo/presentations/`. Not part of the ontology build, the released artifacts, or the production CLI, and never maintained as reusable tools.

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

**Provenance:** original path `metpo/presentations/`; removed by [berkeleybop/metpo#456](https://github.com/berkeleybop/metpo/pull/456); removed from metpo `main` at commit `9ef3859`.

## `literature_mining/` + `metpo-package/metpo/literature_mining/`

The OntoGPT-based literature-mining subsystem: a full working tree (corpus of abstracts and full-text PDFs, extraction configs, OntoGPT/artl-cli outputs, its own Makefile) plus the `metpo.literature_mining` Python package (extraction, grounding, and analysis scripts) that drove it. Used for the ICBO 2025 named-entity-recognition and grounding experiments. Not part of the ontology build or the released ontology.

- `literature_mining/` is the working directory as it stood in metpo (inputs, outputs, corpus, Makefile).
- `metpo-package/metpo/literature_mining/` is the Python package that was under `metpo/literature_mining/` in the source repo, kept under `metpo-package/` here so the two trees stay distinct.

The publication PDFs under `literature_mining/` are open-access (Frontiers, bioRxiv) and were already public in metpo.

**Provenance:** original paths `literature_mining/` and `metpo/literature_mining/`; removed by [berkeleybop/metpo#586](https://github.com/berkeleybop/metpo/pull/586) (umbrella [#433](https://github.com/berkeleybop/metpo/issues/433)).

## `external/`

The non-regenerable pieces of metpo's former `external/` directory. metpo stopped committing that directory (downloaded external ontologies and historical METPO submission OWLs are build artifacts, fetched on demand and now git-ignored). Only the parts that cannot be re-downloaded are archived here:

- `external/ontologies/manual/n4l_merged.owl` — a manually assembled merge (not available from OLS or BioPortal), used as input to the retired embedding pipeline.
- `external/README.md`, `external/databases/README.md` — the directory's original documentation, for context.

The downloaded ontologies (OLS/BioPortal) and the historical METPO submission OWLs are not archived: the former are re-downloadable, and the latter were already processed into `metadata/ontology/historical_submissions/entity_extracts/` (committed in metpo, and what the ID-allocation audit actually reads).

**Provenance:** original path `external/`; removed by the external/ retirement PR (umbrella [berkeleybop/metpo#433](https://github.com/berkeleybop/metpo/issues/433), relates to [#380](https://github.com/berkeleybop/metpo/issues/380)).

## Recovery

To recover any file with its full metpo history instead of this snapshot:

```bash
git -C <metpo-clone> log --all -- <original/path>
```
