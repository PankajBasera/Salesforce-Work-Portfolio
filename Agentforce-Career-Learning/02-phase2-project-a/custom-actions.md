# Project A — Custom Actions Inventory

## Decision guide: Flow vs Apex vs API

| Choose | When |
| --- | --- |
| **Flow** | CRUD with clear steps, admin-maintainable, moderate complexity |
| **Apex invocable** | Complex SOQL, bulk-safe logic, reusable across agents |
| **External API** | Systems of record outside Salesforce (with integration user + error handling) |

## Action 1 — Get Case Context

| Field | Value |
| --- | --- |
| Action label | |
| Implementation | Flow / Apex |
| Inputs | Case Id |
| Outputs | Subject, Description, Status, Priority, Account, Contact, recent Cases, Asset summary |
| Error behavior | Return structured “not found / no access” |

### Implementation sketch (Apex invocable)

```apex
// Sketch only — adapt to your org standards
public with sharing class CaseTriageContextAction {
    @InvocableMethod(label='Get Case Triage Context')
    public static List<Result> run(List<Request> reqs) {
        // Query Case + related with WITH USER_MODE / stripInaccessible
        // Return DTO fields for the agent
        return null;
    }
    public class Request { @InvocableVariable public Id caseId; }
    public class Result {
        @InvocableVariable public String payloadJson;
    }
}
```

---

## Action 2 — Update Triage Fields

| Field | Value |
| --- | --- |
| Action label | |
| Implementation | Flow preferred if simple |
| Allowed fields only | e.g. Triage_Notes__c, Suggested_Priority__c |
| Forbidden | Status=Closed, OwnerId (unless policy), Amount fields |

### Guardrail

- [ ] Field whitelist enforced in Flow decision / Apex allowlist
- [ ] Write uses user mode / FLS respected

---

## Action 3 — Create Follow-up Task

| Field | Value |
| --- | --- |
| Action label | |
| Subject pattern | Triage follow-up: {CaseNumber} |
| WhoId / WhatId | Contact / Case |
| Owner | Case Owner (default) |
| Due date | +1 business day (adjust) |

---

## Wiring into the agent

- [ ] Actions assigned to `Case_Triage` topic
- [ ] Instructions tell agent **when** to call each action
- [ ] Test: action failure surfaces a clear message to the user
