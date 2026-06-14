Severity: Error

Confidence: High

Human Review Required:
- No

Source Trust Level:
- A

Observed Issue:
- A non-interactive element is being used for interactive behavior.

Evidence:
- Click behavior is attached to a non-interactive element.
- The element does not provide native button semantics.
- No equivalent native `button` is used for the same action.

Related Principles:
- Semantic HTML First
- Native Controls First

Related Patterns:
- Omit when no documented pattern applies.

References:
- HTML Living Standard
- WCAG 2.2

Recommendation:
Use a native `button` element when the control triggers an action.

Reasoning:
Native controls provide keyboard and screen reader support.

Remediation Notes:
- Preserve the visible control label when moving to a native `button`.
- Re-check keyboard activation and focus styling after remediation.
