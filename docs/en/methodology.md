# MTD-HX v1 — Cybersecurity Research Methodology
## Full framework usage guide

---

## Why a structured framework?

Unstructured cybersecurity research produces two types of problems:

1. **Technically weak** — Hypotheses without explicit assumptions, no viability analysis, no acknowledgment of limitations. Easy to dismiss.
2. **Ethically compromised** — Without a clear scope and boundary declaration, any analysis can be challenged as facilitating harm.

This framework solves both problems by forcing the researcher to document every decision before making it.

---

## The 8 Phases — Usage Guide

### Phase 1 — Scope Definition
**When:** Before anything else.  
**Purpose:** Define what is in and out of scope, and make an ethical commitment to those boundaries.  
**Common mistake:** Starting from the hypothesis and defining scope afterward. This contaminates analysis with confirmation bias.

### Phase 2 — Verified Facts
**When:** Before formulating hypotheses.  
**Purpose:** Build the factual foundation of the analysis using only publicly verifiable sources.  
**Common mistake:** Mixing facts with inferences. If you don't have a source, it's not a verified fact.

### Phase 3 — Technical Hypothesis
**When:** After documenting facts.  
**Purpose:** Formulate the attack model with explicit assumptions and acknowledged limitations.  
**Common mistake:** Presenting the hypothesis as confirmed fact. Always use conditional language.

### Phase 4 — Taxonomy
**When:** After formulating the hypothesis.  
**Purpose:** Classify the attack using standard frameworks (MITRE ATT&CK, STRIDE). This connects your analysis to industry language.  
**Why it matters:** Allows other researchers and professionals to understand your work without reading the full report.

### Phase 5 — Risk Analysis
**When:** After taxonomy.  
**Purpose:** Evaluate probability × impact per vector. Elevates the analysis from technical to strategic.  
**Common mistake:** Classifying everything as "critical." The risk matrix loses value without differentiation.

### Phase 6 — Recommendations
**When:** After risk analysis.  
**Purpose:** Produce actionable value for each affected stakeholder.  
**Common mistake:** Generic recommendations ("improve security"). Each recommendation must be specific, technical, and directed at the right actor.

### Phase 7 — Legal Framework
**When:** In parallel with others, but document at the end.  
**Purpose:** Map the analysis to applicable legislation and document responsible disclosure.  
**Why it matters:** Without legal grounding, the report may be questioned or ignored by authorities.

### Phase 8 — Final Report
**When:** After completing all previous phases.  
**Purpose:** Consolidate everything into a structured deliverable for authorities, institutions, or publication.  
**Key:** The report must be readable independently. The executive summary is the most important part.

---

## Ethical Principles

1. **Leaked data = always out of scope** — Accessing, downloading, or reproducing illegally obtained data contaminates the entire research and exposes the researcher to legal liability.
2. **Hypothesis ≠ confirmed fact** — A well-supported hypothesis has technical value even without confirmation. Presenting it as confirmed fact destroys it.
3. **Responsible disclosure is part of the process** — Reporting findings to competent authorities is not optional in ethical research.
4. **Acknowledging limitations strengthens the analysis** — A researcher who identifies the limits of their own hypothesis is more credible than one who hides them.

---

*MTD-HX v1 — hoxtxnDev | 2026*
