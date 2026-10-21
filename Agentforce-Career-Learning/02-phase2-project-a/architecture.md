# Project A — Architecture

## Diagram

```mermaid
flowchart TB
  User[Service_Rep]
  Channel[Agent_Channel]
  Agent[Case_Triage_Agent]
  Topic[Topic_Case_Triage]
  Prompts[Prompt_Builder_Templates]
  Actions[Custom_Actions]
  Flow[Flow_or_Apex]
  CRM[(Case_Contact_Asset)]
  Trust[Einstein_Trust_Layer]

  User --> Channel --> Agent --> Topic
  Topic --> Prompts
  Topic --> Actions --> Flow --> CRM
  Prompts --> Trust
  Actions --> Trust
```

## Component notes (fill after build)

| Component | Name in org | Purpose |
| --- | --- | --- |
| Agent | | |
| Topic | | |
| Prompt: Summary | | |
| Prompt: Reply | | |
| Action: GetContext | Flow / Apex: | |
| Action: UpdateTriage | Flow / Apex: | |
| Action: CreateTask | Flow / Apex: | |

## Security context

- Running user / agent user: ____________________
- Object CRUD/FLS considered for: Case, Task, Contact, Asset
- Fields agent may update (whitelist): ____________________
- Fields agent must never update: ____________________

## Hybrid reasoning / deterministic controls

| Control | How I used it |
| --- | --- |
| Filters | |
| Variables | |
| Template expressions | |
| Instruction hard-stops | |

## Failure modes observed

1.
2.
3.

## Why not pure Flow?

> Flow alone cannot interpret messy natural language + multi-turn clarification. The agent uses Flow/Apex as **tools** for deterministic writes; the LLM handles understanding and drafting under guardrails.
