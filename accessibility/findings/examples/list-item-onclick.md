# Finding Example: `li` With Click Behavior

## Input

```jsx
<ul>
  <li onClick={handleSelect}>
    Account settings
  </li>
</ul>
```

## Finding

**Severity:** Warning  
**Confidence:** Medium  
**Human Review Required:** Yes  
**Source Trust Level:** Level A — Authoritative Standards

## Observed Issue

A list item is being used as an interactive control.

## Evidence

- The element is an `li`.
- The element has click behavior through `onClick`.
- The element is inside a list structure.
- No native interactive element is shown inside the list item.
- No keyboard behavior is shown.

## Related Principles

- Semantic HTML First
- Native Controls First
- Keyboard Parity

## Related Pattern

- Non-semantic Interactive Elements

## References

- HTML Living Standard
- WCAG 2.2
- WAI-ARIA Authoring Practices Guide (APG)

## Reasoning

A list item communicates membership in a list. It does not provide native button or link behavior by default.

The correct remediation depends on intent. If the item performs an action, the list item should contain a native `button`. If the item navigates to another location, it should contain a link with an `href`.

This finding requires human review because list items may legitimately contain interactive controls, but the interactive behavior should usually be placed on a native control inside the list item rather than on the `li` itself.

## Recommendation

If the interaction performs an action, use a `button` inside the list item.

```jsx
<ul>
  <li>
    <button type="button" onClick={handleSelect}>
      Account settings
    </button>
  </li>
</ul>
```

If the interaction navigates to a page, use a link inside the list item.

```jsx
<ul>
  <li>
    <a href="/account/settings">
      Account settings
    </a>
  </li>
</ul>
```

## Remediation Notes

- Preserve list semantics when the content is truly a list.
- Place interactive behavior on the appropriate native interactive element.
- Verify keyboard focus reaches the interactive control.
- Verify focus styling is visible.
