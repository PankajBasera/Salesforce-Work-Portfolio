# Interview Talk Track (One Page)

Practice out loud until answers are under ~90 seconds each.

---

### 1. Agent vs Flow vs Apex?

**Answer shape:** Job type → generative need → risk → tooling.

> “If the path is fully known and deterministic, I use Flow or Apex. If the user brings messy language and I need summarize/classify/draft with tools under guardrails, I use Agentforce — with actions implementing the deterministic parts.”

---

### 2. Grounding and quality?

**Answer shape:** Corpus → retrieval → refuse → tests.

> “Grounding is engineering: clean approved content, sensible chunking, retriever filters, and instructions that refuse when nothing relevant is retrieved. I lock it with a Testing Center golden set — paraphrases and out-of-corpus cases included.”

---

### 3. Safety / Trust?

**Answer shape:** Platform + design + human gate.

> “Trust Layer and model controls matter, but I also design least-privilege agent users, whitelist actions and fields, and require explicit approval before customer sends or protected field updates.”

---

### 4. Multi-agent?

**Answer shape:** Split criteria → handoff → tradeoff.

> “I don’t split for novelty. I split when permissions, corpora, or ownership differ — for example Intake classifies, Research stays grounded, writes stay gated. You pay a bit of latency/cost for clearer control and testability.”

---

### 5. Production readiness?

**Answer shape:** Test → deploy together → rollback.

> “Agents, prompts, actions, and corpus version together. Testing Center is a gate. Rollback is deactivate plus restore known-good config — documented in a short runbook.”

---

## Metrics language (customize)

- “Reduced time-to-first-action on triage by ~X% in pilot”
- “≥Y% of drafts accepted with minor edits”
- “Critical refuse cases at 100% on golden suite before activate”
