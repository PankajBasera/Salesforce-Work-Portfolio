# Resume & LinkedIn Pack

Update after each phase. Prefer **credentials first**, then **project bullets with metrics language**.

## Credentials (order of strength)

1. Salesforce Certified Agentforce Specialist — _pending / earned [date]_
2. Agentblazer Legend 2026 — _pending / earned_
3. Agentblazer Innovator 2026 — _pending / earned_
4. Agentblazer Champion 2026 — _pending / earned_

## Skills line (copy/adapt)

Agentforce · Prompt Builder · Agent Builder / Agent Script · custom actions (Flow / Apex) · Data 360 / Data Library grounding · Testing Center · Einstein Trust Layer · multi-agent orchestration (SOMA / MCP / A2A) · sandbox-to-prod agent lifecycle

## Project bullets (pick 2–3)

### Project A — Case Triage Agent
- Designed and built an Agentforce Case Triage Agent with Prompt Builder templates, Flow/Apex actions, and guardrails so reps get summaries and draft replies without unsupervised CRM writes.

### Project B — Ops Co-pilot
- Implemented a human-in-the-loop Ops Co-pilot pattern (draft → explicit approval → gated update) on [Slack / Experience Cloud / Email], targeting faster ops drafts with controlled writes.

### Project C — Grounded Knowledge Agent
- Built a grounded Knowledge/FAQ agent using Data Library retrievers, a Testing Center golden suite, and a sandbox-to-prod deploy/rollback runbook for production-shaped delivery.

### Project D — Coordinated Agents
- Designed a multi-agent pattern (intake/classify → grounded research/draft → human-gated actions), documenting handoffs, permission boundaries, and latency/cost/control tradeoffs vs a monolith agent.

## LinkedIn About (short)

Senior Salesforce developer deepening into Agentforce: designing agents, grounding them with trusted data, testing and staging them for production, and coordinating multi-agent workflows so teams move faster without losing control.

## Experience bullets (paste under current role when true)

- Led / built Agentforce solutions (Champion → Legend path) including Case Triage, Ops Co-pilot (HITL), grounded Knowledge agent, and coordinated multi-agent handoffs.
- Established agent quality gates with Testing Center suites and a deploy runbook covering prompts, actions, corpus sync, and rollback.

## Interview talk track (memorize)

1. **When is an agent the right tool vs Flow or Apex?**  
   Use an agent when the job needs language understanding, variable context, and tool use under guardrails. Prefer Flow/Apex alone for deterministic, fully specified automation with no generative step.

2. **How do you ground and evaluate quality?**  
   Curate corpus → chunk/index → retriever filters → refuse-when-empty instructions → Testing Center golden set (especially paraphrase + out-of-corpus).

3. **How do you keep agents safe?**  
   Trust Layer + least-privilege agent user + action allowlists + deterministic filters/variables + human approval for irreversible or customer-facing sends.

4. **When do you split into multiple agents and how do they coordinate?**  
   Split on trust boundaries, corpora, or ownership. Router/intake classifies and hands off a payload; specialists research/draft; executors (or humans) perform narrow writes.

## Portfolio links

| Item | URL |
| --- | --- |
| This learning kit on GitHub | |
| Demo recording / screenshots | |
| Trailhead profile | |

## Phase resume lines (archive)

| Phase | Line |
| --- | --- |
| 1 | Agentblazer Champion 2026 and built first Agentforce agent in a sandbox. |
| 2 | Designed and built an Agentforce Case Triage Agent with Prompt Builder templates, Flow/Apex actions, and guardrails for safe triage assistance. |
| 3 | Agentblazer Innovator 2026; designed Agentforce solutions with human-in-the-loop approvals tied to operational outcomes. |
| 4 | Agentblazer Legend 2026; built, grounded, tested, and staged Agentforce agents with Data Library retrievers and a sandbox-to-prod deploy runbook. |
| 5 | Multi-agent Agentforce pattern with explicit handoffs; prepared for / earned Agentforce Specialist. |
