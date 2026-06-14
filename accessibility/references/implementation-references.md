# Implementation References

## Purpose

This document lists implementation-oriented references that can support remediation guidance, framework-specific decisions, and tooling recommendations.

These sources are useful, but they do not outrank the standards and higher-trust references listed in [Authoritative Sources](./authoritative-sources.md) and the [Source Trust Model](./source-trust-model.md).

Use implementation references to answer:

- How should this be implemented in a specific framework?
- How does a tool or library behave?
- What constraints exist in a given runtime or component model?

Do not use implementation references to override higher-trust standards or to justify a finding that conflicts with authoritative guidance.

## Official Framework Documentation

### React Documentation

Use for:

- Framework-specific accessibility guidance
- Labeling and form control implementation details
- Component behavior and rendering constraints

### Next.js Documentation

Use for:

- Routing and rendering considerations
- Framework-specific accessibility guidance
- Application structure that affects semantics or focus management

## Official Tooling Documentation

### axe-core

Use for:

- Automated accessibility testing behavior
- Rule descriptions and limitations
- CI and linting integration guidance

Notes:

- Automated testing supplements manual review.
- Tool output is evidence of a detected rule violation, not a substitute for broader usability review.

### Testing Library Documentation

Use for:

- Query strategies aligned with accessibility semantics
- Test patterns based on roles, names, and labels
- Verification of accessible behavior in component tests

### ESLint Accessibility Plugin Documentation

Use for:

- Lint rule behavior
- Static-analysis guardrails
- Tooling constraints in code review workflows

Notes:

- Lint rules can identify implementation risks, but they are not normative accessibility standards.

## When to Cite These Sources

Use implementation references when:

- The finding is already supported by a higher-trust source and implementation detail is needed.
- A recommendation depends on a framework or tool constraint.
- The documentation explains how to apply a standards-based recommendation in practice.

Escalate to human review when:

- Tool guidance appears to conflict with a specification.
- A framework abstraction obscures the actual accessibility behavior.
- The available implementation documentation is incomplete or indirect.
