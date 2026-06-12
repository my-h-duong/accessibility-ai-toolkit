# Accessibility Principles

## Purpose

This overview defines the core principles that guide accessibility findings, patterns, checklists, and remediation recommendations in this repository.

Use this document to answer:

- What outcome are we trying to protect?
- Why is a recommendation preferred?
- Which principle should shape a finding or workflow?

Principles are durable guidance. They explain intent and decision-making, not one-off implementation details.

## How This Document Relates to Other Docs

- Principles explain why an approach is preferred.
- Patterns explain how a recurring implementation problem should be handled.
- Checklists help reviewers inspect work consistently.
- Workflows define how reviews should be conducted and documented.
- References identify the sources that can support a finding.
- Findings should connect observed evidence to one or more principles and to the repository's source trust model.

## Principles

### Semantic HTML First

Prefer semantic HTML before introducing ARIA or custom interaction patterns.

Semantic HTML provides built-in structure, expected interaction behavior, and stronger support across browsers and assistive technologies. Native semantics are also easier to maintain and usually require less custom code.

Apply this principle when deciding:

- Whether a `button` should be used instead of a clickable `div`
- Whether a `fieldset` and `legend` should group related inputs
- Whether headings, lists, tables, and landmarks are expressed with native elements

Implication for findings:

- Treat unnecessary replacement of native semantics as a risk.
- Prefer recommendations that simplify markup rather than layer on ARIA.

### Native Controls First

Use native browser controls whenever possible.

Native controls usually provide:

- Keyboard support
- Focus behavior
- Platform semantics
- Expected interaction models
- Stronger default compatibility with assistive technology

Custom controls may be necessary, but they raise the implementation burden. When a native control can meet the requirement, it is usually the preferred option.

Implication for findings:

- Recommend native elements before custom widgets.
- Treat custom controls as needing stronger evidence and more complete validation.

### Visible Information Preferred

Information users need to complete a task should be visible at the point of need.

Avoid hiding critical instructions in:

- Tooltips
- Placeholder text
- Hover-only interactions
- Icon-only affordances without visible explanation
- Expand-on-demand content when the information is required for task completion

Users should not have to remember hidden instructions while entering information. Keeping important guidance visible reduces cognitive load and supports users across screen sizes, input modes, and assistive technologies.

Implication for findings:

- Flag instructions that disappear, are hard to rediscover, or are available only through one interaction mode.
- Prefer persistent help text over hidden hints when the information is necessary for success.

### Preserve Accessible Names

Accessible names should align with visible labels whenever possible.

When extra context is needed, provide it through grouping, descriptions, and supporting relationships rather than by replacing the visible label with a longer programmatic label.

This helps:

- Sighted and non-sighted users reference the same control consistently
- Voice input users target controls more reliably
- Reviewers reason about labels with less ambiguity

Implication for findings:

- Distinguish between the control's label and its contextual description.
- Prefer `aria-describedby`, group labels, headings, or `legend` over replacing the accessible name.

### Meaningful Grouping and Relationships

Related content and controls should be grouped in ways that are clear both visually and programmatically.

Users need to understand:

- Which controls belong together
- Which instructions apply to which fields
- Which error message belongs to which input
- Which heading or section provides context for the current task

Grouping can come from native HTML structure, headings, `fieldset` and `legend`, descriptive relationships, and predictable layout patterns.

Implication for findings:

- Look for missing contextual relationships in repeated fields, composite controls, and complex forms.
- Prefer structural solutions before ARIA-only solutions.

### Keyboard Parity

Anything available with a mouse, pointer, or touch interaction must also be available with a keyboard.

Users must be able to:

- Reach controls
- Understand focus location
- Activate controls
- Dismiss overlays when appropriate
- Exit interactive regions
- Complete the same task without pointer input

Implication for findings:

- Evaluate the full interaction, not just tab stops.
- Treat pointer-only functionality as a material accessibility risk.

### Clear Error Recovery

Users should be able to identify, understand, and recover from errors.

Errors should:

- Identify the affected field or action
- Explain what went wrong
- Explain how to fix it
- Be programmatically associated with the relevant control
- Be reachable from any error summary when one is present

Error handling should reduce confusion, not add it. Users should not need to infer which field failed or what correction is required.

Implication for findings:

- Separate "error exists" from "error is understandable and actionable."
- Prefer recommendations that improve both association and clarity.

### Accessibility Supports Usability

Accessibility improvements should make the interface easier to understand and use, not just technically conformant.

Meeting a technical requirement is important, but users still need to:

- Understand what to do
- Find the relevant information
- Recover from mistakes
- Complete the task with reasonable effort

When multiple compliant solutions exist, prefer the one that reduces user effort, preserves clarity, and creates more consistent behavior.

Implication for findings:

- Explain user impact, not only standards impact.
- Avoid recommendations that are technically valid but harder to understand or maintain.

### Evidence Over Assumption

Findings should be based on observable evidence and supported by trustworthy references.

This repository uses the [Source Trust Model](../references/source-trust-model.md) to determine what evidence is strong enough for a finding.

Implication for findings:

- Do not infer missing behavior without stating the uncertainty.
- Do not treat AI-generated explanation, community opinion, or habit as authoritative evidence.
- Escalate to human review when confidence is limited or the guidance is ambiguous.

## Using Principles in Reviews

When documenting a finding:

1. Identify the observable issue.
2. Match the issue to one or more principles.
3. Confirm the finding against an appropriate reference level.
4. Recommend the simplest valid remediation that preserves semantics and usability.

Principles should narrow the reasoning behind a finding. They should not replace evidence, standards, or implementation-specific review.
