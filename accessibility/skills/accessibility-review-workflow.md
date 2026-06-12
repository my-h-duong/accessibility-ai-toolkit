# Accessibility Review Workflow

## Purpose

This workflow defines the review process used when evaluating code, designs, components, pages, or user interfaces for accessibility.

The goal is to produce findings that are evidence-based, reference-backed, and actionable.

---

## Review Process

### Step 1 — Gather Evidence

Inspect the implementation and identify observable behavior.

Collect evidence before drawing conclusions.

Examples:

- HTML structure
- Semantic elements
- Accessible names
- Keyboard behavior
- Focus management
- Error handling
- Labels and descriptions
- Color contrast
- ARIA usage

Questions:

- What exists?
- What is missing?
- What behavior can be observed?

Do not generate findings without evidence.

---

### Step 2 — Identify Applicable Principles

Determine which accessibility principles apply.

Examples:

- Semantic HTML First
- Native Controls First
- Preserve Accessible Names
- Visible Information Preferred
- Accessibility Supports Usability

Questions:

- Which principle is relevant?
- Is the implementation aligned with the principle?

---

### Step 3 — Match Known Patterns

Determine whether the implementation matches a documented accessibility pattern.

Examples:

- Repeated Fields
- Error Summaries
- Non-semantic Interactive Elements
- Modal Dialogs
- Form Validation

Questions:

- Does a documented pattern exist?
- Is the pattern implemented correctly?

---

### Step 4 — Consult Authoritative Sources

Validate findings against trusted references.

Use the Source Trust Model to determine source priority.

Preferred order:

1. Standards and specifications
2. Government guidance
3. Implementation references
4. Community guidance
5. AI inference

Questions:

- Is the finding supported by authoritative guidance?
- Does a conflicting source exist?
- Which source has higher authority?

---

### Step 5 — Generate Findings

Create findings based on evidence and references.

Each finding should include:

- Severity
- Evidence
- References
- Recommendation
- Reasoning
- Human review status

Avoid unsupported claims.

---

### Step 6 — Assign Confidence

Assign confidence based on evidence quality.

### High Confidence

- Directly observable
- Supported by authoritative sources
- Minimal interpretation required

### Medium Confidence

- Strong indication of an issue
- Additional context may affect the outcome

### Low Confidence

- Subjective concern
- Limited evidence
- Human validation required

Confidence should reflect evidence quality, not certainty of opinion.

---

### Step 7 — Recommend Remediation

Provide actionable recommendations.

Recommendations should:

- Prefer native HTML
- Prefer simpler solutions
- Preserve accessibility semantics
- Minimize implementation complexity

When multiple valid solutions exist:

- Explain tradeoffs
- Identify preferred approaches
- Require human review when necessary

---

## Output Requirements

Every finding must include:

- Severity
- Confidence
- Evidence
- Source trust level
- References
- Recommendation
- Reasoning
- Human review required
- Related principle
- Related pattern when applicable

---

## Review Philosophy

The workflow should:

- Prefer evidence over assumptions
- Prefer standards over opinions
- Prefer native solutions over custom solutions
- Prefer usability over technical compliance alone
- Explain why a finding exists
- Provide references whenever possible

The workflow should not:

- Invent requirements
- Invent references
- Assume compliance
- Treat AI inference as authoritative evidence
- Present uncertain findings as facts
