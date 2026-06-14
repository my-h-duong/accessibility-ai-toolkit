# Finding Example: `div` With `role="button"`

## Input

```jsx
<div
  role="button"
  tabIndex={0}
  onClick={handleSubmit}
  onKeyDown={handleKeyDown}
>
  Submit
</div>
```

## Finding

**Severity:** Warning  
**Confidence:** Medium  
**Human Review Required:** Yes  
**Source Trust Level:** Level A — Authoritative Standards

## Observed Issue

A non-semantic `div` is being used to recreate button behavior.

## Evidence

- The element is a `div`.
- The element uses `role="button"`.
- The element is made focusable with `tabIndex={0}`.
- The element has click behavior through `onClick`.
- The element appears to include custom keyboard handling through `onKeyDown`.
- A native `button` would likely provide the same interaction with less custom behavior.

## Related Principles

- Semantic HTML First
- Native Controls First
- Keyboard Parity
- Preserve Accessible Names

## Related Pattern

- Non-semantic Interactive Elements

## References

- HTML Living Standard
- WCAG 2.2
- WAI-ARIA Specification
- WAI-ARIA Authoring Practices Guide (APG)

## Reasoning

This implementation attempts to add button semantics and keyboard access to a non-semantic element. That is better than a plain clickable `div`, but it still recreates behavior that a native `button` already provides.

The custom implementation must correctly handle focus, keyboard activation, disabled behavior, accessible naming, and interaction expectations. Because these details are easy to miss, a native `button` is usually the safer and more maintainable choice.

## Recommendation

Use a native `button` unless there is a strong reason for a custom implementation.

```jsx
<button type="button" onClick={handleSubmit}>
  Submit
</button>
```

If the control submits a form, prefer:

```jsx
<button type="submit">
  Submit
</button>
```

## Remediation Notes

- Verify whether the custom implementation is necessary.
- Verify keyboard activation works with expected keys.
- Verify visible focus styling is present.
- Verify disabled behavior is handled if applicable.
- Prefer native HTML when it provides the required interaction.
