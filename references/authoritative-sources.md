# Authoritative Sources

## Purpose

This document identifies the highest-trust source categories used to support accessibility findings in this repository.

These sources should be preferred over tutorials, blog posts, conference talks, forum answers, and AI-generated explanations.

Use this document together with the [Source Trust Model](./source-trust-model.md), which defines source priority and conflict resolution.

Implementation-oriented documentation is listed separately in [Implementation References](./implementation-references.md).

## How to Use This Document

Use authoritative sources when you need to support:

- Standards-based findings
- Semantic HTML guidance
- ARIA usage rules
- Public-sector accessibility interpretation
- Claims about required behavior or conformance

If a source is helpful for implementation but is not the highest-trust authority for the claim, place it in the implementation references document instead of treating it as primary evidence.

## Authoritative Standards and Specifications

### WCAG

#### Description

The Web Content Accessibility Guidelines define internationally recognized accessibility requirements for digital experiences.

#### Use For

- Accessibility requirements
- Success criteria
- Conformance levels
- Outcome-based evaluation

#### Preferred Version

WCAG 2.2

#### Notes

WCAG defines the required outcome, but it does not always prescribe a single implementation.

### HTML Living Standard

#### Description

The HTML Living Standard is the primary specification for HTML elements, semantics, and document structure.

#### Use For

- Element validity
- Semantic HTML
- Native control behavior
- Document structure
- Accessibility-related HTML behavior

#### Notes

When determining whether markup is valid or whether a native element is appropriate, prefer this source over tutorials, linter messages, or framework abstractions.

### WAI-ARIA Specification

#### Description

The WAI-ARIA specification defines how accessibility information can be exposed when native HTML semantics are insufficient.

#### Use For

- ARIA roles
- ARIA states
- ARIA properties
- Accessibility API mappings

#### Notes

ARIA should supplement native HTML rather than replace it when a native solution exists.

### Accessible Name and Description Computation

#### Description

This specification defines how accessible names and descriptions are derived from labels, content, and ARIA attributes.

#### Use For

- Accessible name behavior
- Accessible description behavior
- Label and description precedence

#### Notes

Use this source when evaluating how a control is named or described programmatically.

## Government and Public-Sector Guidance

### Section 508

#### Description

Section 508 defines accessibility requirements for United States federal information and communication technology.

#### Use For

- Federal accessibility requirements
- Compliance-oriented interpretation
- Public-sector expectations

#### Notes

Section 508 often aligns with WCAG but may be consulted for public-sector implementation context.

### U.S. Access Board Guidance

#### Description

The U.S. Access Board publishes guidance related to accessibility requirements and interpretation in public-sector contexts.

#### Use For

- Public-sector accessibility interpretation
- Compliance context
- Government-oriented explanatory guidance

## Standards-Adjacent Guidance

### WAI-ARIA Authoring Practices Guide (APG)

#### Description

The APG provides implementation guidance and patterns for interactive components.

#### Use For

- Dialogs
- Menus
- Tabs
- Accordions
- Comboboxes
- Widget interaction expectations

#### Notes

The APG is strong guidance, but it is not a substitute for WCAG, HTML, or ARIA specifications when a claim depends on normative requirements.

## Non-Authoritative Sources

The following may provide useful context but should not be treated as primary evidence for a finding:

- Blog posts
- Tutorials
- Forum discussions
- Community examples
- Conference presentations
- Social media posts
- AI-generated content

These sources may help explain a concept, but they should not be the sole basis for a standards-based accessibility finding.
