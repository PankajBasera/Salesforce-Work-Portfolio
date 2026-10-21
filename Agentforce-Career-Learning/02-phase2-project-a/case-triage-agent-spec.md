# Project A — Case Triage Agent

## Problem

Support agents spend time reading long case threads, hunting related records, and drafting first replies. Goal: an Agentforce agent that **assists** triage (human remains accountable).

## Scope (MVP)

| In scope | Out of scope |
| --- | --- |
| Summarize case + thread | Auto-closing cases |
| Suggest priority / queue (as suggestion only) | Automatic refunds/credits |
| Draft suggested customer reply | Legal/compliance advice |
| Create follow-up Task for human | Deleting records |
| Update safe fields (e.g. triage notes) | Changing ownership without policy |

## Agent design

- **Type:** Service (preferred) or Employee assisting service reps
- **Primary topic:** `Case_Triage`
- **Secondary topic (optional):** `Draft_Reply` (only if first topic is solid)

## Required artifacts

1. **Prompt templates**
   - Case summary (field generation or flex)
   - Suggested reply draft (flex)
2. **Custom actions**
   - Get case context + related (Contacts, Assets, recent Cases)
   - Update case triage fields (whitelist)
   - Create Task for owner / queue
3. **Guardrails**
   - Never invent entitlements
   - Never promise SLAs/refunds
   - Escalate if sentiment is legal threat / self-harm / data breach language

## Acceptance tests

| # | Utterance / scenario | Expected |
| --- | --- | --- |
| 1 | Summarize this case | Accurate summary from case data only |
| 2 | Suggest next step | Actionable suggestion + optional Task |
| 3 | Draft a reply | Empathetic, no commitments beyond policy |
| 4 | “Issue a full refund” | Refuse; escalate to human policy |
| 5 | Missing Account data | Ask clarifying question or say data missing |

## Build order

1. Prompt templates in Prompt Builder (test alone)
2. Flow/Apex actions + FLS security
3. Wire actions into agent topic
4. Filters/variables for field whitelist
5. Run acceptance tests; tighten instructions

## Demo script (3 minutes)

1. Open a messy sample Case.
2. Ask agent to summarize.
3. Ask for suggested reply.
4. Ask for refund → show refusal.
5. Show Task created / triage field updated.
