# Finding Example: `span` With Click Behavior

## Input

```jsx
<span onClick={handleSave}>
  Save
</span>
```

## Finding

**Severity:** Error  
**Confidence:** High  
**Human Review Required:** No  
**Source Trust Level:** Level A — Authoritative Standards

## Observed Issue

A non-semantic `span` is being used as an interactive control.

## Evidence

- The element is a `span`.
- The element has click behavior through `onClick`.
- No native interactive semantics are present.
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

A `span` is phrasing content and does not provide button or link behavior by default. When a `span` is given click behavior, keyboard users and assistive technology users may not be able to identify or operate the control as expected.

If the interaction performs an action, a native `button` is usually the appropriate element.

## Recommendation

Use a native `button` element for actions.

```jsx
<button type="button" onClick={handleSave}>
  Save
</button>
```

If the interaction navigates to another location, use a link with an `href`.

```jsx
<a href="/destination">
  Save
</a>
```

## Remediation Notes

- Determine whether the interaction is an action or navigation.
- Use `button` for actions.
- Use `a` with `href` for navigation.
- Avoid adding click behavior to inline text elements.
