# Use-Case Backlog (8–10 ideas)

Score each 1–5. Prioritize high scores on **Repetitive**, **Tool-backed**, and **Measurable**. Star top 2 for a work pilot.

| # | Use case (one sentence) | Domain | Repetitive | Tool-backed | Measurable | Risk if wrong | Priority | Star |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Case triage summary + draft reply for messy threads | Service | 5 | 5 | 5 | Med | 15 | ★ |
| 2 | Opportunity next-step coach for AEs (tasks + talk track) | Sales | 4 | 4 | 4 | Low–Med | 12 | |
| 3 | Knowledge-grounded internal FAQ for employees | Internal | 5 | 4 | 4 | Low | 13 | |
| 4 | Lead enrichment summary before first call | Sales | 4 | 3 | 3 | Low | 10 | |
| 5 | Contract / order status explainer (read-only) | Service | 5 | 5 | 4 | Med | 14 | |
| 6 | Bug/defect intake classifier → suggest queue + Task | Ops | 4 | 5 | 4 | Med | 13 | ★ |
| 7 | Meeting notes → Task + follow-up email draft | Internal | 4 | 3 | 3 | Low | 10 | |
| 8 | Policy Q&A grounded in approved docs only | Compliance-adjacent | 3 | 4 | 3 | High | 10 | |
| 9 | Ops Co-pilot: draft field/status change with APPROVE UPDATE gate | Ops | 5 | 5 | 5 | Med | 15 | |
| 10 | Renewal risk brief from Account + Opportunity + Cases | Sales | 3 | 4 | 4 | Med | 11 | |

## Scoring guide

- **Repetitive:** Happens often; humans hate the busywork
- **Tool-backed:** Clear Salesforce actions exist (query, update whitelist, create Task)
- **Measurable:** Time saved, deflection, CSAT, or draft-accept rate
- **Risk if wrong:** Prefer human-in-the-loop when High
- **Priority:** Sum of Repetitive + Tool-backed + Measurable (max 15)

## Top 2 (starred) — why

### Pilot A — Case triage summary + draft reply
- **Use case:** Assist reps with summarize → suggest next step → draft reply on high-volume Cases
- **Success metric:** Median time-to-first-meaningful-action down 30–50%; ≥70% of drafts accepted with minor edits
- **Why Agentforce (not Flow alone):** Unstructured thread + variable tone needs generative draft; Flow alone cannot summarize and reason over messy context safely without an LLM step

### Pilot B — Bug/defect intake classifier
- **Use case:** Classify inbound defect Cases, suggest queue, create follow-up Task; human confirms assignment
- **Success metric:** Correct queue suggestion ≥80% on golden set; handoff SLA improved
- **Why Agentforce (not Flow alone):** Classification benefits from free-text understanding; keep assignment write behind human confirmation (Project B pattern)

## Rejected / deferred (optional)

| Idea | Why not now |
| --- | --- |
| Auto-send customer email | High reputational risk; keep draft-only until Trust + QA mature |
| Auto-refund / credit | Policy/finance ownership; guardrail refuse forever in MVP |
| Legal/compliance advice beyond approved KB | High risk; grounded Q&A only with citation + human review |
