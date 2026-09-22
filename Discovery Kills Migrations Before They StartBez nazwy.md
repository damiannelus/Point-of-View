## Why Discovery Fails

Legacy migration projects fail before a single line of code is moved. The root cause isn't technical debt or tooling — it's a distorted starting picture inherited from a broken investigation phase.

**Two instruments, same failure mode:**

- **Human reviewers** skip coverage due to bias, fatigue, and incomplete institutional memory
- **LLMs** pattern-match on surface signals — imports, file names, documentation — and hallucinate missing runtime context rather than declaring unknowns

> Both humans and LLMs narrate what they infer, not what they can prove.

---

## The Fix: Evidence Before Interpretation

Pre-defined, quantified assessment — run before any human or LLM interpretation begins.

### Wide Scan First

- Map the full dependency graph
- Surface coupling metrics (Ca/Ce, instability)
- Identify change frequency by module
- No shortcuts, same path every time

### Deep Focus Second

- Direct expert attention to load-bearing modules
- Prioritise high-churn files and indirect coupling flagged by tooling
- Interpretation happens after measurement — never before

---

## The Strongest Objection

Deterministic tooling produces a swamp of data with no inherent insight. **Accepted** — which is why the harness defines the flow and tool sequence in advance. The output is scoped evidence, not a raw dump.

---

## The Ask

Pressure-test the predefined flow: does the tool sequence produce sufficient signal for an expert to make load-bearing decisions without reverting to inference?