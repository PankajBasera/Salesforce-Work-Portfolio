# Channel Practice Notes (Phase 3)

Pick **one** channel for Project B. Document constraints so interview answers are concrete.

## Choice

| Field | Value |
| --- | --- |
| Chosen channel | Slack / Experience Cloud / Email (circle one) |
| Why this channel for my role | |
| Primary users | |
| Auth / identity notes | |

## Channel-specific constraints

### Slack
- Message length and formatting (markdown vs plain)
- Who can invoke the agent (workspace, channels, DMs)
- How approval (“APPROVE UPDATE”) is captured in-thread
- Link-back to Salesforce record required in every draft

### Experience Cloud
- Guest vs authenticated user permissions
- What CRM data the community user may never see
- Branding / tone for external audiences
- Escalation path when agent refuses

### Email
- Draft-only vs send-capable (MVP = draft)
- Signature / disclaimer requirements
- Threading and Case Email Message association
- PII and Trust Layer redaction expectations

## Demo checklist for chosen channel

- [ ] User can request a draft from the channel
- [ ] Agent returns proposal + rationale
- [ ] Write to protected fields blocked without confirmation
- [ ] Confirmation path works once
- [ ] Failure / no-access message is clear

## Interview one-liner

> “I deployed the Ops Co-pilot on **[channel]** so users stay in their workflow; writes stay gated behind explicit approval.”
