# Source Trust Model

## Purpose

This document defines how the toolkit evaluates accessibility guidance, resolves conflicting information, and determines what evidence is acceptable when producing findings.

The goal is to prevent findings from relying on outdated, unofficial, unsupported, or AI-inferred claims.

---

## Trust Levels

### Level A — Authoritative Standards

Use Level A sources as the highest authority for accessibility, semantic HTML, ARIA, and browser-platform behavior.

**Examples**

* WCAG
* W3C
* WHATWG HTML Living Standard
* WAI-ARIA Specifications
* WAI-ARIA Authoring Practices Guide (APG)

**Use For**

* Required accessibility behavior
* Semantic HTML validity
* Accessible name and description rules
* ARIA usage
* WCAG success criteria
* Standards-based claims

---

### Level B — Government and Public Sector Guidance

Use Level B sources for public-sector implementation guidance and compliance interpretation.

**Examples**

* Section 508
* U.S. Access Board Guidance
* USWDS Accessibility Guidance
* Government Digital Service Guidance

**Use For**

* Public-sector accessibility expectations
* Government implementation guidance
* Design system accessibility guidance
* Compliance-oriented recommendations

---

### Level C — Framework and Tool Documentation

Use Level C sources for framework-specific implementation details.

**Examples**

* React Documentation
* Next.js Documentation
* Testing Library Documentation
* axe-core Documentation
* ESLint Accessibility Plugin Documentation

**Use For**

* Framework-specific implementation guidance
* Testing guidance
* Tool behavior
* Linter behavior
* Library-specific constraints

> Level C sources must not override Level A or Level B sources.

---

### Level D — Community Guidance

Use Level D sources only as supplemental context.

**Examples**

* Blog posts
* Tutorials
* Conference talks
* Community examples
* Forum answers

**Use For**

* Additional explanation
* Historical context
* Practical examples

> Level D sources should not be used as the primary basis for accessibility findings.

---

### Level E — AI Inference

Use Level E only when the model is reasoning from observed evidence and no direct source is available.

**Examples**

* Pattern recognition
* Usability judgment
* Design critique
* Risk assessment
* Hypothesis generation

> Level E findings should require human review unless supported by stronger evidence.

---

## Conflict Resolution

When sources conflict, use this priority order:

1. Current specifications and standards
2. Current WCAG guidance
3. Current government or public-sector guidance
4. Framework or tool documentation
5. Community guidance
6. AI inference

### Simplified Rule

```txt
Spec > Standard > Government Guidance > Framework Docs > Community Guidance > AI Inference
```

---

## Recency Rules

Sources can become outdated.

When using a source:

* Prefer the most current stable version available.
* Do not rely on deprecated guidance.
* Include version information when relevant.
* Prefer newer authoritative guidance over older authoritative guidance.

**Examples**

* WCAG 2.2
* WCAG 2.1
* HTML Living Standard
* ARIA 1.2
* React 19
* Next.js 15

---

## Finding Requirements

Every finding should include:

* Observed issue
* Supporting evidence
* Severity
* Confidence
* Source trust level
* References
* Recommendation
* Reasoning
* Human review status

---

## Confidence Guidance

Confidence should be based on evidence quality, not how strongly the AI believes something.

### High Confidence

Use when:

* The issue is directly observable.
* The source is Level A or Level B.
* The recommendation is well-established.
* Human interpretation is minimal.

**Example**

A `div` with click behavior is being used as a button when a native `button` is appropriate.

---

### Medium Confidence

Use when:

* The issue is likely but context may matter.
* The source is strong, but implementation details are incomplete.
* The finding depends on user flow, design intent, or surrounding code.

**Example**

Repeated fields appear to lack group context, but the rendered accessibility tree has not been verified.

---

### Low Confidence

Use when:

* The issue is subjective.
* The source is indirect.
* The implementation context is incomplete.
* The finding depends heavily on human judgment.

**Example**

Help text may be too complex for users, but no content design standard is available.

---

## Human Review Rules

Human review is required when:

* The finding is based primarily on Level D or Level E evidence.
* The issue depends on user intent or product context.
* The implementation cannot be fully evaluated from the available code.
* The recommendation could affect legal, compliance, or policy interpretation.
* Multiple valid solutions exist.

Human review may not be required when:

* The issue is directly observable.
* The source is Level A.
* The remediation is standard and low risk.

---

## Prohibited Source Behavior

The toolkit must not:

* Treat AI output as authoritative evidence.
* Prefer blog posts over official specifications.
* Cite outdated guidance when newer authoritative guidance exists.
* Present uncertain claims as definitive.
* Claim legal compliance or certification.
* Invent WCAG mappings.
* Invent source references.
* Use community articles as the sole basis for an error-level finding.

---

## Example Finding

### Finding

**Severity:** Error
**Confidence:** High
**Human Review Required:** No

#### Evidence

* Element is a `div`
* Element has click behavior
* Native `button` would provide equivalent interaction

#### Source Trust Level

Level A — Authoritative Standards

#### References

* HTML Living Standard
* WCAG 2.2
* WAI-ARIA Authoring Practices Guide

#### Recommendation

Use a native `button` element.

#### Reasoning

A native button provides semantic meaning, keyboard support, focus behavior, and expected assistive technology behavior without requiring custom ARIA or keyboard handling.
