---
name: accessible-spa-form-patterns
description: WCAG 2.2 AA patterns for client-side form handling, labels, focus, and text safety
metadata:
  type: feedback
---

**Rule:** Every form input must have a visible, programmatically-associated label using `for` and `id`. Use `:focus-visible` for focus styles, not `:focus`. Never insert user text with `innerHTML`; use `textContent` instead.

**Why:** WCAG 2.2 AA requires programmatically-associated labels (not placeholders), visible focus indicators on keyboard interaction (2.4.7), and prevention of XSS via textContent. Placeholder text disappears when users type and fails screen reader detection.

**How to apply:** 
- Label pattern: `<label for="inputId">Label text</label><input id="inputId" ...>`
- Focus: Use `input:focus-visible { outline: 2px solid var(--focus-color); }` — this applies only to keyboard focus, respecting user preferences
- Text safety: In JS form handlers or dynamic content, always use `element.textContent = userInput` not `.innerHTML`
- Use `aria-describedby`, `aria-required="true"`, and `role="alert"` for form messages
- Confirmation messages after submission should be announced with `aria-live="polite"` containers
- For data that is not user-provided (tool names in grid, category labels), `textContent` is still the safest default

Tested in October 2026 on WCAG 2.2 AA single-page app with no external dependencies.
