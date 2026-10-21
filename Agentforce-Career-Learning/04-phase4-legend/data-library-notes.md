# Project C — Data Library & Retriever Notes

Capture design choices so you can explain grounding quality in interviews.

## Corpus

| Field | Value |
| --- | --- |
| Source type | Knowledge / Files / Other |
| Approximate doc count | |
| Owner / stewards | |
| Refresh cadence | |
| Languages | |

## Chunking & indexing

| Decision | Choice | Why |
| --- | --- | --- |
| Chunk size strategy | | |
| Overlap | | |
| Heading-aware splits | Yes / No | |
| Metadata retained (title, URL, category) | | |
| Excluded content | Drafts, outdated, legal-hold | |

## Retriever behavior

| Field | Value |
| --- | --- |
| Retriever name | |
| Top-k / result count | |
| Filters (category, data category, record type) | |
| Observed latency (approx) | |

## Quality experiments (run ≥3)

| Experiment | Change | Result on golden Qs |
| --- | --- | --- |
| 1 | | |
| 2 | | |
| 3 | | |

## Failure modes observed

| Failure | Symptom | Mitigation |
| --- | --- | --- |
| Wrong chunk | | Tighten filters / rewrite headings |
| Empty retrieval | | Add synonyms / improve titles |
| Hallucination despite retrieval | | Harder instructions; require cite-or-refuse |
| Stale policy | | Content ops + library refresh |

## Interview talk track

> “We treated grounding as an engineering problem: corpus hygiene, chunking, retriever filters, and a refuse-when-empty instruction — then locked quality with Testing Center golden cases.”
