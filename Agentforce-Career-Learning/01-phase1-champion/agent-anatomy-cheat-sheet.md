# Agent Anatomy Cheat Sheet (one page)

Fill this after your first agent. Keep it to one screen for interviews.

## One-sentence job

> This agent exists to: _______________________________________________

## Building blocks

| Piece | What it is | My agent |
| --- | --- | --- |
| **Agent type** | Employee / Service (exam focus) | |
| **Channel** | Where users talk (UI, Slack, email, Experience, voice, API) | |
| **Topic** | A job the agent can take on (scope + instructions) | |
| **Instructions** | Natural-language rules for how to behave in that topic | |
| **Actions** | Tools the agent can call (standard / Flow / Apex / API) | |
| **Grounding** | Data the LLM is allowed to use (CRM, Knowledge, Data Library) | |
| **Variables / filters** | Deterministic controls (hybrid reasoning) | |
| **Guardrails** | What it must never do; Trust Layer + permissions | |
| **Escalation** | When to stop and hand to a human | |

## Request → response flow (draw or fill)

```
User utterance
    → Topic classification / routing
        → Reasoning (hybrid: LLM + Agent Script / filters)
            → Action(s) if needed
                → Grounded answer or state change
                    → Channel response / escalate
```

My notes on where it failed in testing:
1.
2.
3.

## When to use an agent vs Flow vs Apex

| Use… | When… |
| --- | --- |
| **Flow / Apex** | Deterministic, high-volume, clear rules, no language understanding needed |
| **Prompt template alone** | One-shot generation into a field/email (no multi-turn tool use) |
| **Agent** | Multi-turn, tool use, ambiguous language, needs judgment + actions |
| **Multi-agent** | Clear specialist boundaries, different permissions, or scale/control needs |

## Trust Layer (must explain)

- Masks / protects sensitive data in generative AI calls
- Model access can be restricted (which models are allowed)
- Grounding + permissions still matter: agent runs in a security context

## Interview sound bite (30 seconds)

> “An Agentforce agent is a scoped worker: topics define jobs, instructions set policy, actions are tools (often Flow/Apex I already own), grounding supplies trusted data, and Trust Layer plus filters keep behavior safe. I start with one narrow job, measure quality in Testing Center, then only split into multiple agents when permissions or specialist depth demand it.”
