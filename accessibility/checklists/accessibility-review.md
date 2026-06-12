# Accessibility Review Checklist

## Purpose

Use this checklist to identify accessibility issues during component reviews, pull request reviews, design reviews, and manual testing.

This checklist should be used alongside applicable principles, patterns, and authoritative references.

---

# Structure & Semantics

## Document Structure

* Headings communicate page and section hierarchy.
* Heading levels are not skipped without justification.
* Content order is meaningful.
* Landmark regions are present when appropriate.
* Semantic HTML is used whenever possible.

## Semantic Elements

* Buttons use `button` elements.
* Links use `a` elements.
* Lists use `ul`, `ol`, and `li`.
* Tables use appropriate table markup.
* Form controls use native elements where possible.
* ARIA is not replacing available native semantics.

---

# Keyboard Accessibility

## Keyboard Navigation

* All interactive elements are keyboard accessible.
* Interactive elements can be activated using expected keyboard interactions.
* Keyboard focus can reach all functionality.

## Focus Management

* Focus indicators are visible.
* Focus order follows the visual and logical reading order.
* Focus is managed appropriately during dynamic interactions.
* Focus is not unexpectedly moved or lost.

## Keyboard Traps

* Users can navigate into and out of all interactive regions.
* No keyboard traps are present.

---

# Forms

## Labels & Accessible Names

* Every form control has an accessible name.
* Visible labels are present when appropriate.
* Accessible names match visible labels.
* Labels remain understandable out of context.

## Instructions & Help Text

* Instructions are available when needed.
* Critical instructions remain visible.
* Required fields are clearly identified.
* Formatting requirements are communicated before submission.

## Validation & Errors

* Errors are programmatically associated with fields.
* Error messages are understandable and actionable.
* Error summaries link to affected fields when present.
* Validation feedback is announced to assistive technologies when appropriate.

## Repeated Fields

* Repeated field groups provide sufficient context.
* Group relationships are conveyed programmatically.
* Accessible names remain consistent with visible labels.

---

# Visual Accessibility

## Color & Contrast

* Text meets required contrast ratios.
* Interactive controls meet required contrast ratios.
* Information is not conveyed by color alone.

## Zoom & Reflow

* Content remains usable at 200% zoom.
* Content reflows appropriately at smaller viewport sizes.
* Horizontal scrolling is minimized where possible.

## Responsive Behavior

* Content remains understandable across screen sizes.
* Interactive elements remain accessible on touch devices.

---

# Dynamic Content

## Announcements

* Important status changes are communicated to assistive technologies.
* Dynamic updates are announced when appropriate.

## Modals & Dialogs

* Focus moves into dialogs when opened.
* Focus returns appropriately when dialogs close.
* Background content is not interactable while modal dialogs are active.

---

# Content & Usability

## Readability

* Instructions are clear and concise.
* Error messages explain how to resolve issues.
* Labels and headings are understandable.

## User Understanding

* Users can determine what information is required.
* Users can understand the purpose of controls.
* Users can complete tasks without relying on visual-only cues.

---

# Review Notes

For each issue identified:

* Gather evidence.
* Match against applicable principles.
* Match against applicable patterns.
* Validate against authoritative references.
* Assign confidence.
* Recommend remediation.
* Indicate whether human review is required.
