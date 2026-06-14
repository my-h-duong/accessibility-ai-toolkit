# Finding Severity And Confidence

This guide defines how to assign severity, confidence, and human review status for accessibility findings.

Use it with the [finding template](./templates/finding-template.md) so findings stay consistent across review contexts.

## Severity

Severity describes the impact and urgency of the issue if the observation is correct.

### Error

Use `Error` when the issue is a clear accessibility defect that is likely to block, mislead, or materially impair task completion.

Typical signals:

- Native semantics are replaced with incorrect custom behavior.
- Users may be unable to operate a control with expected input methods.
- Important information is missing or inaccessible.

### Warning

Use `Warning` when the issue creates meaningful accessibility risk, but the impact may depend on surrounding context or may not fully block task completion.

Typical signals:

- Context is incomplete but the implementation appears risky.
- The issue may confuse users or reduce reliability across assistive technology.
- A stronger structural solution is likely needed, even if a minimal fallback exists.

### Suggestion

Use `Suggestion` when the issue is a quality improvement rather than a clear defect.

Typical signals:

- Usability could be improved without evidence of a direct failure.
- The implementation is technically acceptable but less clear or less durable than the preferred approach.
- A recommendation would strengthen consistency or maintainability.

### Needs Review

Use `Needs Review` when a potential issue has been identified but there is not enough evidence to classify it confidently as an error, warning, or suggestion.

Typical signals:

- The rendered behavior has not been verified.
- The available evidence is incomplete or indirect.
- Design intent or runtime behavior materially affects the outcome.

## Confidence

Confidence describes how strong the evidence is behind the finding, not how severe the issue would be.

### High

Use `High` confidence when:

- The issue is directly observable.
- The evidence is concrete and specific.
- The references clearly support the conclusion.

### Medium

Use `Medium` confidence when:

- The issue is likely, but some contextual uncertainty remains.
- The evidence is meaningful but incomplete.
- The recommendation is strong, but the final classification still depends on verification.

### Low

Use `Low` confidence when:

- The finding depends on assumptions or indirect evidence.
- The available implementation context is limited.
- Human interpretation is needed before treating the issue as established.

## Severity Versus Confidence

Severity and confidence answer different questions.

- Severity asks: if this finding is correct, how serious is the problem?
- Confidence asks: how well supported is the finding by the available evidence?

A finding can be:

- high severity and low confidence
- low severity and high confidence
- medium confidence regardless of severity

Do not increase severity just because confidence is high. Do not lower confidence just because the issue is minor.

## Human Review Required

Set `Human Review Required` to `Yes` when:

- the finding relies on incomplete evidence
- the issue depends on intent, runtime behavior, or nuanced interpretation
- the references do not fully settle the recommendation
- the finding is marked `Needs Review`

Set `Human Review Required` to `No` when:

- the issue is directly observable
- the evidence is sufficient to support the conclusion
- the recommendation is well established by trusted references

## Example: Non-Semantic Interactive Element

### Example A

Observed issue:

- A `div` is being used as a click target for an action that should be performed by a button.

Evidence:

- The element has click behavior.
- The element does not provide native button semantics.
- No equivalent native control is present.

Recommended classification:

- Severity: `Error`
- Confidence: `High`
- Human Review Required: `No`

Reasoning:

- If the control is action-triggering UI, replacing a native button with a non-semantic element is a direct accessibility defect.
- The evidence is observable and the recommendation is well established.

### Example B

Observed issue:

- A visually styled custom element appears interactive in a design review artifact, but keyboard behavior and rendered semantics have not been verified.

Evidence:

- The artifact suggests click-based behavior.
- No implementation or accessibility tree evidence is available.

Recommended classification:

- Severity: `Needs Review`
- Confidence: `Low`
- Human Review Required: `Yes`

Reasoning:

- The pattern is potentially serious, but the available evidence is too limited to confirm the defect.
