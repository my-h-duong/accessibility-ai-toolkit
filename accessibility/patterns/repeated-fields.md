# Repeated Fields

## Status

Active

## Category

Forms

## Problem

Forms may contain repeated groups of fields that share identical labels.

Example:

```txt
Contact Person 1
  First Name
  Last Name

Contact Person 2
  First Name
  Last Name
```

While the visible labels are correct, assistive technology users may have difficulty understanding which group a field belongs to when navigating through the form.

## Context

Repeated field groups commonly appear in:

* Contact lists
* Household members
* Project locations
* Team members
* References
* Emergency contacts

The challenge is not that the field labels are incorrect.

The challenge is providing sufficient context to distinguish one instance of a repeated field from another.

## Preferred Solution

Preserve the visible label as the accessible name.

Provide additional context through semantic grouping and descriptive relationships.

Preferred techniques include:

* `fieldset` and `legend`
* `aria-describedby`
* Section headings
* Programmatic relationships to group labels

## Avoid

Avoid replacing a correct visible label with a longer `aria-label` solely to provide group context.

Example:

```html
<input aria-label="Contact Person 1 First Name" />
```

This replaces the field's accessible name rather than supplementing it with contextual information.

## Reasoning

The field label and the grouping information serve different purposes.

The field label identifies the control:

```txt
First Name
```

The grouping information provides context:

```txt
Contact Person 1
```

Users benefit from hearing both pieces of information rather than combining them into a single label.

Preserving the accessible name also keeps the programmatic label aligned with the visible label presented to sighted users.

## Good Example

```html
<h3 id="contact-person-1">
  Contact Person 1
</h3>

<label for="first-name-1">
  First Name
</label>

<input
  id="first-name-1"
  aria-describedby="contact-person-1"
/>
```

## Better Example

```html
<fieldset>
  <legend>Contact Person 1</legend>

  <label for="first-name-1">
    First Name
  </label>

  <input id="first-name-1" />
</fieldset>
```

When a native grouping element is appropriate, prefer native HTML.

## Accessibility Review Guidance

When reviewing repeated field groups:

* Verify each field has an appropriate visible label.
* Verify users can determine which group a field belongs to.
* Prefer semantic grouping before ARIA solutions.
* Ensure contextual information is available to assistive technology users.
* Confirm visible labels and accessible names remain aligned.

## References

Reference Level: A

* WCAG 2.2
* WAI-ARIA Authoring Practices Guide (APG)
* HTML Living Standard

## Related Principles

* Native HTML First
* Preserve Accessible Names
* Evidence Over Opinion
