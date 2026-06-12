# Preserve Accessible Names

## Status

Active

## Category

Forms, Semantics, Accessibility

## Purpose

Users of assistive technologies rely on accessible names to identify controls, understand their purpose, and navigate interfaces efficiently.

Whenever possible, the accessible name should align with the visible label presented to users.

## Principle

Preserve the visible label as the accessible name.

Additional context should be provided separately rather than replacing or modifying the label itself.

## Why It Matters

Visible labels serve as the primary identifier for form controls and interactive elements.

When the visible label and accessible name differ significantly, users may experience:

- Confusing screen reader announcements
- Increased cognitive load
- Mismatches between visible instructions and announced content
- Difficulties following support documentation
- Challenges communicating issues with support staff or team members

Consistency between what users see and what assistive technologies announce improves usability for everyone.

## Preferred Approach

Use the visible label as the primary accessible name.

When additional context is needed, provide it through:

- Semantic grouping
- Fieldset and legend
- Section headings
- `aria-describedby`
- Supporting instructional text

The goal is to supplement the label, not replace it.

## Examples

### Preferred

Visible label:

```txt
First Name
```

Accessible name:

```txt
First Name
```

Additional context:

```txt
Contact Person 1
```

provided through semantic grouping or descriptive relationships.

### Preferred

```html
<fieldset>
  <legend>Contact Person 1</legend>

  <label for="first-name">
    First Name
  </label>

  <input id="first-name" />
</fieldset>
```

### Preferred

```html
<h3 id="contact-person-1">
  Contact Person 1
</h3>

<label for="first-name">
  First Name
</label>

<input
  id="first-name"
  aria-describedby="contact-person-1"
/>
```

### Avoid

```html
<label for="first-name">
  First Name
</label>

<input
  id="first-name"
  aria-label="Contact Person 1 First Name"
/>
```

when the additional text is only being used to provide grouping context.

## Common Scenarios

This principle frequently applies to:

- Repeated field groups
- Dynamic forms
- Multi-step forms
- Editable tables
- Contact lists
- Household member forms
- Emergency contact forms
- Team member management interfaces

## Accessibility Review Guidance

When reviewing a component:

- Verify a visible label exists.
- Verify the accessible name matches the visible label.
- Verify additional context is provided separately.
- Verify grouping information remains available to assistive technologies.
- Verify labels are not unnecessarily replaced with `aria-label`.

## Exceptions

There are situations where `aria-label` is appropriate.

Examples include:

- Icon-only buttons
- Controls without visible text
- Situations where no visible label exists

In these cases, the accessible name may be provided programmatically.

## Related Patterns

- Repeated Fields
- Form Validation
- Error Summaries
- Dynamic Form Sections

## Related Principles

- Semantic HTML First
- Visible Information Preferred

## References

Reference Level: A

- WCAG 2.2
- WAI-ARIA Specification
- WAI-ARIA Authoring Practices Guide (APG)
- HTML Living Standard
