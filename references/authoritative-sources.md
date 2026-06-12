# Authoritative Sources

## Purpose

This document identifies the primary sources used by the Accessibility AI Toolkit when evaluating accessibility findings, recommendations, and implementation guidance.

These sources should be preferred over community articles, tutorials, blog posts, conference presentations, or AI-generated explanations.

When multiple sources conflict, follow the rules defined in `source-trust-model.md`.

---

# Accessibility Standards

## WCAG

### Description

The Web Content Accessibility Guidelines (WCAG) define internationally recognized accessibility requirements for digital experiences.

### Use For

* Accessibility requirements
* Success criteria
* Conformance levels
* Accessibility testing guidance

### Preferred Version

WCAG 2.2

### Notes

WCAG defines what outcomes must be achieved but does not always prescribe a specific implementation.

---

# Semantic HTML

## HTML Living Standard

### Description

The HTML Living Standard is the authoritative specification for HTML elements, semantics, and document structure.

### Use For

* Element validity
* Semantic HTML
* Document structure
* Native control behavior
* Accessibility-related HTML behavior

### Notes

When determining whether markup is valid, prefer the HTML Living Standard over blog posts, tutorials, or linter recommendations.

---

## WHATWG

### Description

The Web Hypertext Application Technology Working Group (WHATWG) maintains the HTML Living Standard.

### Use For

* HTML specifications
* Browser behavior
* Modern web platform standards

### Notes

The HTML Living Standard should generally be treated as the authoritative HTML reference.

---

# ARIA

## WAI-ARIA Specification

### Description

Defines how accessibility information can be exposed to assistive technologies when native HTML semantics are insufficient.

### Use For

* ARIA roles
* ARIA states
* ARIA properties
* Accessibility APIs

### Notes

ARIA should supplement native HTML rather than replace it whenever possible.

---

## WAI-ARIA Authoring Practices Guide (APG)

### Description

Provides implementation guidance and accessibility patterns for common user interface components.

### Use For

* Dialogs
* Menus
* Tabs
* Accordions
* Comboboxes
* Interactive widgets

### Notes

The APG provides implementation guidance and patterns but is not a replacement for WCAG or HTML specifications.

---

# Government Accessibility Guidance

## Section 508

### Description

United States federal accessibility requirements for information and communication technology.

### Use For

* Federal accessibility requirements
* Government compliance guidance
* Public-sector accessibility expectations

### Notes

Section 508 frequently references WCAG requirements but may include additional compliance considerations.

---

# Framework Documentation

## React Documentation

### Use For

* Framework-specific accessibility guidance
* React implementation details
* Component behavior

---

## Next.js Documentation

### Use For

* Next.js accessibility guidance
* Routing behavior
* Framework implementation details

---

# Accessibility Testing Tools

## axe-core

### Use For

* Automated accessibility testing
* Common accessibility rule validation
* Accessibility linting and CI workflows

### Notes

Automated testing should supplement, not replace, manual accessibility review.

---

# Source Selection Guidelines

When evaluating a finding:

1. Prefer authoritative standards.
2. Prefer official documentation over community interpretations.
3. Prefer current versions over historical guidance.
4. Prefer evidence-backed findings over assumptions.
5. Escalate to human review when guidance is ambiguous.

---

# Non-Authoritative Sources

The following may provide useful context but should not be treated as primary evidence:

* Blog posts
* Tutorials
* Forum discussions
* Stack Overflow answers
* Conference presentations
* Social media posts
* AI-generated content

These sources may be used to explain a concept but should not be used as the sole justification for an accessibility finding.
