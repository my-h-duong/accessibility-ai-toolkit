# Persistent Help Text

## Status

Active

## Category

Forms, Content, Instructions

## Problem

Users often need instructions, constraints, definitions, or examples to complete a form field correctly.

When that guidance is hidden in tooltips, placeholder text, expandable hints, or hover-only UI, users may not discover it, may lose access to it while entering data, or may be forced to remember it instead of referencing it at the point of need.

## Context

Persistent help text is commonly needed when a field requires:

- Specific formatting
- Eligibility details
- Definitions of unfamiliar terms
- Privacy or data-use explanations
- File or document requirements
- Clarification about what to enter or avoid

The challenge is not simply whether help text exists.

The challenge is whether the information remains available when users need it to understand the field, complete the task, and recover from mistakes.

## Preferred Solution

Display important help text persistently near the related field.

The preferred placement is usually:

- Between the field label and the form control
- Immediately below the label
- Immediately below the control when that is the established design-system pattern

Help text should be:

- Visible by default when it is required for completion
- Programmatically associated with the related field when appropriate
- Written clearly and directly
- Available before submission
- Available while users are entering or reviewing information

Preferred techniques include:

- Visible supporting text adjacent to the field
- `aria-describedby` when the help text supplements the field
- Native grouping such as `fieldset` and `legend` when the help applies to a set of controls

## Avoid

Avoid using tooltip-only instructions for information required to complete a field.

Avoid using placeholder-only instructions because placeholder text:

- Disappears when users type
- May be mistaken for entered content
- Often has lower contrast
- Is not a reliable substitute for labels or help text

Avoid hover-only help because it may not be available to keyboard, touch, or mobile users.

Avoid requiring users to open a disclosure or modal just to access instructions needed for basic data entry unless the extra content is optional or truly secondary.

## Reasoning

Instructions should be available at the point of need.

Persistent help text reduces memory burden and helps users understand expectations before they make an error. It also makes the form more resilient across input methods, viewport sizes, and assistive technologies.

Hidden or disappearing instructions increase cognitive load and can make forms harder to complete, especially for users with memory, attention, vision, motor, or screen reader access needs.

## Good Example

```html
<label for="email">Email address</label>

<p id="email-help">
  Use an address you check regularly. Updates will be sent here.
</p>

<input
  id="email"
  type="email"
  aria-describedby="email-help"
/>
```

## Better Example

```html
<fieldset>
  <legend>Upload supporting document</legend>

  <p id="document-help">
    Provide a PDF file under 10 MB. Remove passwords before uploading.
  </p>

  <label for="document">Choose file</label>
  <input
    id="document"
    type="file"
    aria-describedby="document-help"
  />
</fieldset>
```

When instructions apply to multiple related controls, prefer native grouping.

## Avoid Example

```html
<label for="email">Email address</label>

<input
  id="email"
  type="email"
  placeholder="We will use this address to send updates"
/>
```

```html
<label for="email">Email address</label>

<button type="button" aria-label="Help">?</button>

<input id="email" type="email" />
```

## Accessibility Review Guidance

When reviewing persistent help text:

- Verify required instructions are visible without hover.
- Verify users can access the guidance while interacting with the field.
- Verify help text is associated with the relevant control when needed.
- Verify placeholder text is not serving as the primary instruction.
- Verify the label, help text, and error messaging each serve distinct roles.

## Finding Guidance

Use this pattern when a finding involves any of the following:

- Required instructions that disappear during entry
- Help available only through tooltip, hover, or icon-triggered affordances
- Placeholder text being used as the main source of instructions
- Field requirements that become clear only after validation fails

Finding framing:

- Describe what information users need.
- Describe where that information currently appears.
- Explain why the current presentation is not reliably available at the point of need.
- Recommend a persistent, visible, and associated alternative.

Common evidence to capture:

- The visible label
- The location and trigger for the help content
- Whether the help remains available while typing
- Whether the help is exposed programmatically to assistive technologies

## References

Reference Level: A

- WCAG 2.2
- HTML Living Standard
- WAI-ARIA Authoring Practices Guide (APG)

## Related Principles

- Visible Information Preferred
- Meaningful Grouping and Relationships
- Accessibility Supports Usability
- Evidence Over Assumption
