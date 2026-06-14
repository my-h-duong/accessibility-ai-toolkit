Severity: Error

Confidence: High

Observed Issue:
- A non-interactive element is being used for interactive behavior.

Evidence:
- Click behavior is attached to a non-interactive element.
- The element does not provide native button semantics.

Source Trust Level:
- A

References:
- HTML Living Standard
- WCAG 2.2

Related Principle:
- Semantic HTML First

Recommendation:
Use a native `button` element when the control triggers an action.

Reasoning:
Native controls provide keyboard and screen reader support.

Human Review Required:
- No
