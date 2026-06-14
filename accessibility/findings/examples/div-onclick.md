# Finding Example: `div` With Click Behavior

## Input

```jsx
<div onClick={handleSubmit}>
  Submit
</div>
```

## Finding

**Severity:** Error  
**Confidence:** High  
**Human Review Required:** No  
**Source Trust Level:** Level A — Authoritative Standards

## Observed Issue

A non-semantic `div` is being used as an interactive submit control.

## Evidence

- The element is a `div`.
- The element has click behavior through `onClick`.
- No native button semantics are present.
- No keyboard behavior is shown.
- The visible text suggests the control performs an action.

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
- WAI-ARIA Authoring Practices Guide (APG)

## Reasoning

A submit action should use a native interactive element. A `div` does not provide button semantics, expected keyboard interaction, or default assistive technology support.

A native `button` provides the expected semantics and behavior without requiring custom ARIA, focus, or keyboard handling.

## Recommendation

Use a native `button` element.

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

- Prefer native HTML over adding ARIA to a `div`.
- Keep the visible label, `Submit`, as the accessible name.
- Verify the control is reachable and operable by keyboard after the change.
