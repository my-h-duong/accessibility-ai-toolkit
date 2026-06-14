# Non-semantic Interactive Elements

## Status

Active

## Category

Interaction, Semantics, Keyboard Accessibility

## Applies To

- Design
- Development

## Problem

Interfaces sometimes attach interactive behavior to elements that are not interactive by default.

Examples include:

```html
<div onClick="...">Save</div>
<span onClick="...">Save</span>
<li onClick="...">Save</li>
```

These elements may visually appear interactive, but they do not provide native interactive semantics, expected keyboard behavior, or default assistive technology support.

## Context

Non-semantic interactive elements commonly appear when developers style generic elements to look like buttons, links, tabs, menu items, or other controls.

The problem is not only that the element is missing ARIA.

The deeper problem is that the implementation is recreating behavior that native HTML already provides.

## Preferred Solution

Use the native HTML element that matches the interaction.

Common mappings:

| User intent | Preferred element |
| --- | --- |
| Perform an action | `button` |
| Navigate to a URL | `a` with `href` |
| Select an option from a set | Native form control or appropriate composite widget pattern |
| Submit a form | `button type="submit"` |
| Trigger a non-submit action | `button type="button"` |

Prefer native controls before adding ARIA, custom keyboard handling, or custom focus behavior.

## Avoid

Avoid attaching interactive behavior to non-interactive elements when a native element is available.

```html
<div onClick="...">Submit</div>
```

Avoid using ARIA to recreate a native element without a strong reason.

```html
<div role="button" tabIndex="0" onClick="...">
  Submit
</div>
```

While this may expose some button semantics, it still requires the implementation to correctly recreate keyboard behavior, focus behavior, disabled behavior, and expected interaction patterns.

## Edge Cases

A non-semantic element with `role="button"`, `tabIndex="0"`, and keyboard event handling may be closer to accessible than a plain clickable `div`.

However, it should still be reviewed because native HTML is usually simpler, more reliable, and easier to maintain.

This pattern should distinguish between:

- Clear errors where no native semantics or keyboard support are present.
- Warnings where custom semantics are partially implemented.
- Needs-review cases where the custom implementation may be justified but requires verification.

## Reasoning

Native interactive elements provide behavior that users and assistive technologies expect.

For example, a native `button` provides:

- Button semantics
- Keyboard focusability
- Expected keyboard activation
- Assistive technology support
- Disabled state support
- Form behavior when applicable
- Platform-consistent interaction behavior

Recreating this behavior manually increases the risk of missing required interaction details.

## Good Example

```html
<button type="button" onClick="...">
  Save
</button>
```

## Form Submit Example

```html
<button type="submit">
  Submit
</button>
```

## Avoid Example

```html
<div onClick="...">
  Submit
</div>
```

## Needs Review Example

```html
<div
  role="button"
  tabIndex="0"
  onClick="..."
  onKeyDown="..."
>
  Submit
</div>
```

This implementation may include some accessibility support, but reviewers should verify whether a native `button` would be more appropriate.

## Accessibility Review Guidance

When reviewing custom interactive elements:

- Verify whether a native element would provide the same interaction.
- Verify the element has appropriate semantics.
- Verify the element is keyboard reachable.
- Verify the element supports expected keyboard activation.
- Verify focus indicators are visible.
- Verify the accessible name matches the visible label.
- Verify disabled behavior is handled if applicable.
- Prefer a native element when there is no strong reason for a custom implementation.

## Finding Guidance

This pattern may produce different finding levels depending on the implementation.

### Error

Use when:

- A non-interactive element has click behavior.
- No native interactive element is used.
- No keyboard support is present.
- A native control would provide the same behavior.

Example:

```html
<div onClick="...">Submit</div>
```

### Warning

Use when:

- A non-semantic element has partial interactive semantics.
- `role`, `tabIndex`, or keyboard handlers are present.
- A native element would still be simpler or more reliable.

Example:

```html
<div role="button" tabIndex="0" onClick="...">
  Submit
</div>
```

### Needs Review

Use when:

- A custom widget may be justified.
- The implementation depends on surrounding code.
- Keyboard behavior, focus behavior, or accessible name cannot be verified from the available snippet.

## References

Reference Level: A

- HTML Living Standard
- WCAG 2.2
- WAI-ARIA Specification
- WAI-ARIA Authoring Practices Guide (APG)

## Related Principles

- Semantic HTML First
- Native Controls First
- Keyboard Parity
- Preserve Accessible Names
