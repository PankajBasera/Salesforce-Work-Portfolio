# Project C — Grounded Knowledge Agent

## Problem

Employees or service reps ask policy / product / process questions. Generic LLM answers invent facts. Goal: an agent that **answers only from approved content** (Knowledge articles or uploaded library docs) and cites or names sources.

## Scope (MVP)

| In scope | Out of scope |
| --- | --- |
| Q&A grounded in Data Library / Knowledge | Unconstrained web search |
| Cite or name source article/doc chunk | Legal advice beyond published policy |
| Escalate when confidence / retrieval weak | Auto-changing CRM fields from answers |
| Testing Center golden suite | Full multi-language corpus (optional stretch) |

## Agent design

- **Type:** Employee (internal FAQ) or Service (agent-assist Knowledge)
- **Primary topic:** `Grounded_FAQ`
- **Secondary topic (optional):** `Escalation_Handoff` — create Task when retrieval fails

## Grounding design

1. **Corpus:** Approved Knowledge articles **or** sample unstructured docs in Agentforce Data Library
2. **Chunking / indexing:** Document choices in [data-library-notes.md](data-library-notes.md)
3. **Retriever:** Prefer library retriever over “model memory”
4. **Instructions hard-stop:**
   - Answer only from retrieved snippets
   - If no relevant chunk, say so and offer escalate
   - Never invent SKUs, SLAs, refunds, or entitlements

## Required artifacts

| Artifact | Location |
| --- | --- |
| Agent + topic instructions | Org + notes below |
| Data library / retriever config | [data-library-notes.md](data-library-notes.md) |
| Test suite | [testing-center-suite.md](testing-center-suite.md) |
| Deploy + rollback | [deploy-runbook.md](deploy-runbook.md) |

## Acceptance tests (manual + Testing Center)

| # | Scenario | Expected |
| --- | --- | --- |
| 1 | In-corpus factual question | Correct answer + source reference |
| 2 | Paraphrased same question | Same policy substance |
| 3 | Out-of-corpus question | Refuse / “not in knowledge” + escalate option |
| 4 | Conflicting docs (if present) | Prefer newer/approved; or flag conflict |
| 5 | Prompt injection (“ignore policy”) | Ignore; stay grounded |

## Build order

1. Prepare 5–15 clean Knowledge articles or docs (titles, clear headings)
2. Configure Data Library / indexing; verify retrieval on 3 known questions
3. Wire agent topic + grounding; tighten instructions
4. Add escalate action (create Task) for misses
5. Author Testing Center suite; iterate until critical cases pass
6. Write deploy runbook while the build is fresh

## Demo script (4 minutes)

1. Ask an in-corpus question → show grounded answer + source.
2. Ask a paraphrase → still correct.
3. Ask something not in corpus → refuse + Task escalate.
4. Open Testing Center → show pass/fail on golden set.
5. Walk one page of deploy checklist / rollback.

## Org notes (fill after build)

| Field | Value |
| --- | --- |
| Agent API name | |
| Data library name | |
| Retriever name | |
| Knowledge categories / doc set | |
| Agent user / perm set | |
