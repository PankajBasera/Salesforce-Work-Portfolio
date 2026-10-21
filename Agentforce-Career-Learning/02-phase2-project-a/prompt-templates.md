# Project A — Prompt Templates

Paste final Prompt Builder text here after you activate templates in the org.

## Template 1 — Case Summary

- **API / Label:**
- **Type:** Field Generation / Flex
- **Inputs / merge fields:**
- **Grounding:**

```
SYSTEM / INSTRUCTIONS:
You summarize Salesforce Cases for support agents.
Only use the provided case fields and related context.
Be concise: Issue, Impact, What was tried, Open questions.
Do not invent entitlements, SLAs, or product facts.
If data is missing, say what is missing.

USER / CONTEXT:
Case Number: {!...}
Subject: {!...}
Description: {!...}
Status / Priority: {!...}
Related context: {!...}
```

### Activation / execution notes

- Who can run it:
- Where it is invoked (agent action / record page / flow):

---

## Template 2 — Suggested Reply

- **API / Label:**
- **Type:** Flex (recommended)
- **Inputs / merge fields:**
- **Grounding:**

```
SYSTEM / INSTRUCTIONS:
Draft a customer-facing reply for a human agent to edit and send.
Tone: clear, empathetic, professional.
Never promise refunds, credits, timelines, or legal outcomes.
If policy is unclear, include a bracketed NOTE FOR AGENT.
Keep under 150 words unless complexity requires more.

USER / CONTEXT:
Case summary: {!...}
Customer name: {!...}
Known facts: {!...}
```

### Activation / execution notes

-

---

## Prompt engineering checklist

- [ ] Clear role + audience
- [ ] Explicit do / don’t list
- [ ] Grounding sources named
- [ ] Output format specified
- [ ] Tested with empty / partial inputs
- [ ] Trust Layer / model access reviewed
