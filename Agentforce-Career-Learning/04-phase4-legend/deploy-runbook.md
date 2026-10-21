# Project C — Deploy Runbook (Sandbox → Staging → Prod)

Short operational checklist for agents, prompt templates, and grounding assets. Adapt names to your org’s ALM (change sets, DevOps Center, unlocked packages, etc.).

## Principles

1. **Treat agents like apps:** version prompts, topics, actions, and library content together.
2. **Never deploy grounding corpus without re-running tests.**
3. **Prefer activate in lower env first;** same acceptance suite in each env.
4. **Rollback means known-good config + content**, not “turn it off and hope.”

## Pre-deploy checklist

### Configuration inventory

| Item | API / Label | Version / notes | Included? |
| --- | --- | --- | --- |
| Agent definition | | | [ ] |
| Topics / instructions | | | [ ] |
| Prompt templates | | | [ ] |
| Custom actions (Flow/Apex) | | | [ ] |
| Permission sets / agent user | | | [ ] |
| Data library / retriever | | | [ ] |
| Knowledge / docs sync | | | [ ] |
| Testing Center suite export / notes | | | [ ] |

### Quality gates

- [ ] Testing Center suite green in source sandbox (critical 100%)
- [ ] FLS / CRUD reviewed for agent running user
- [ ] Guardrails: refunds, legal, PII — spot-checked
- [ ] Channel (Slack / ECC / email) smoke-tested if in scope
- [ ] Stakeholders: support lead + admin aware of change window

## Deploy sequence (recommended)

1. **Freeze** content edits on library docs during cutover window (or tag a content version).
2. Deploy **code/metadata** (Apex, Flow, permission sets) first.
3. Deploy / sync **prompt templates**; activate only after validation.
4. Deploy **agent** definition (topics, actions wiring).
5. Sync **Data Library / Knowledge** corpus to match tested version.
6. Run **Testing Center** (or manual golden set) in target env.
7. Enable channel / activate agent for pilot users (not whole org on day one).
8. Monitor first 24–48 hours (failure rate, escalate volume, user feedback).

## Smoke tests in target env (minimum)

| # | Test | Owner | Pass? |
| --- | --- | --- | --- |
| 1 | In-corpus question returns grounded answer | | [ ] |
| 2 | Out-of-corpus refuses | | [ ] |
| 3 | Escalate Task creates successfully | | [ ] |
| 4 | Permission-denied path is graceful | | [ ] |
| 5 | Channel entry point works | | [ ] |

## Rollback thinking

### Triggers to rollback

- Critical test failures after deploy
- Spike in wrong answers / user complaints
- Security / Trust Layer incident
- Broken action (writes wrong fields)

### Rollback steps

1. **Deactivate** agent or remove from channel (fastest user-facing stop).
2. Restore previous **agent + prompt** versions from source control / prior package.
3. Revert **library content** to last known-good snapshot if corpus caused drift.
4. Re-run smoke tests on restored stack.
5. Postmortem: which gate failed (content, prompt, action, perms)?

### What “known good” means

| Artifact | Where stored | Last good ID |
| --- | --- | --- |
| Agent export / metadata | Git / packaging | |
| Prompt templates | Git / packaging | |
| Apex/Flow | Git | |
| Corpus snapshot note | Data library notes | |

## Monitoring (first week)

| Signal | Where to look | Action threshold |
| --- | --- | --- |
| Error / failed actions | Debug logs / monitoring | Investigate same day |
| Escalate Task volume | Report | Unexpected spike → review retrieval |
| User thumbs-down / feedback | Channel / survey | Triage weekly |
| Test suite drift | Re-run after content change | Block if critical fail |

## Go / no-go (sign-off)

| Role | Name | Go? | Date |
| --- | --- | --- | --- |
| Builder | | | |
| Admin / release | | | |
| Business owner | | | |

## Interview one-liner

> “My Agentforce deploy runbook versions prompts, actions, and corpus together, gates on Testing Center, and rollback is deactivate-plus-restore-known-good — not a hope-based fix.”
