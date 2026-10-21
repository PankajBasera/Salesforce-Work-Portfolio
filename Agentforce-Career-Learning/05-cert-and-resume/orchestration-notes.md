# Multi-Agent Orchestration Notes (SOMA / MCP / A2A)

Exam weight is small (~5%); **career weight is high**. Capture definitions in your words after studying official docs/trails.

## When one agent is enough

- Shared permission boundary
- One grounding corpus
- One release owner / test suite
- Topics are facets of the same job (e.g. summarize + draft reply)

## When to split (SOMA — single-org multi-agent)

- Different trust levels (read FAQ vs write Opportunities)
- Different corpora (HR policy vs product Knowledge)
- Different teams own prompts/actions
- You need isolated Testing Center suites

## Concept map (fill definitions after study)

| Concept | What it is (my words) | When I’d use it |
| --- | --- | --- |
| SOMA | Multiple agents in one Salesforce org coordinating a job | Intake vs Research split |
| MCP | | Tool/server interoperability pattern for agents |
| A2A | | Agent-to-agent communication pattern |
| Router / specialist / executor | Router classifies; specialist reasons; executor has narrow writes | Project D |

## Practical checklist for any multi-agent design

- [ ] Clear owner agent for the user-facing conversation
- [ ] Explicit handoff payload (ids, intent, confidence)
- [ ] No ambient “all agents can do everything” perm set
- [ ] Per-agent test suites + a thin end-to-end path
- [ ] Human escalation path defined before go-live

## Links to revisit

- Agentblazer / Agentforce docs on multi-agent orchestration (current release)
- Exam guide section: Multi-Agent Orchestration
- Your Project D write-up: [project-d-coordinated-agents.md](project-d-coordinated-agents.md)

## Interview closer

> “I split agents on trust and release boundaries, not for novelty — Intake classifies, Research stays grounded, writes stay human-gated.”
