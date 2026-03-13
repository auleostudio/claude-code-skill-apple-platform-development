# WAI-ARIA Practices Reference

Core ARIA roles, patterns, and keyboard interaction guidance from the W3C ARIA Authoring Practices Guide (APG).

## The Rules of ARIA

### Rule 1: Don't Use ARIA If You Can Use Native HTML
Native HTML elements have built-in semantics, keyboard handling, and AT support. Prefer `<button>` over `<div role="button">`.

### Rule 2: Don't Change Native Semantics
Don't add a role to override an element's native semantics unless absolutely necessary.
```html
<!-- Bad -->
<h2 role="tab">Tab heading</h2>

<!-- Good -->
<div role="tab"><h2>Tab heading</h2></div>
```

### Rule 3: All Interactive ARIA Controls Must Be Keyboard Operable
If you create a widget with ARIA, you must implement keyboard interaction.

### Rule 4: Don't Use role="presentation" or aria-hidden="true" on Focusable Elements
Never hide visible, focusable elements from the accessibility tree.

### Rule 5: All Interactive Elements Must Have an Accessible Name
Every interactive element needs a name via label, aria-label, or aria-labelledby.

## Landmark Roles

Use landmarks to define page structure. Assistive tech users navigate by landmarks.

| HTML Element | ARIA Role | Purpose |
|-------------|-----------|---------|
| `<header>` (top-level) | `banner` | Site-wide header |
| `<nav>` | `navigation` | Navigation links |
| `<main>` | `main` | Primary content (one per page) |
| `<aside>` | `complementary` | Supporting content |
| `<footer>` (top-level) | `contentinfo` | Site-wide footer |
| `<section>` (with label) | `region` | Perceivable section |
| `<form>` (with label) | `form` | Form landmark |
| — | `search` | Search functionality |

### Landmark Best Practices
- Every page must have a `main` landmark
- Use `<nav>` with aria-label for multiple navigation regions
- Label landmarks when multiple of the same type exist
- Don't nest landmarks of the same type

## Accessible Names and Descriptions

### Naming Methods (Priority Order)
1. `aria-labelledby` — references visible text by ID
2. `aria-label` — string label (use when no visible label)
3. `<label>` element — for form controls
4. `title` attribute — tooltip (least reliable, avoid as sole name)
5. Native text content — button text, link text, alt text

### Descriptions
- `aria-describedby` — references supplementary text by ID
- Use for instructions, error messages, or additional context

```html
<label for="email">Email</label>
<input id="email" type="email" aria-describedby="email-hint">
<span id="email-hint">We'll never share your email.</span>
```

## Common Widget Patterns

### Dialog (Modal)
```html
<div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
  <h2 id="dialog-title">Confirm Action</h2>
  <p>Are you sure?</p>
  <button>Confirm</button>
  <button>Cancel</button>
</div>
```
**Keyboard:** Tab cycles within dialog. Escape closes. Focus trapped inside.

### Tabs
```html
<div role="tablist" aria-label="Settings">
  <button role="tab" aria-selected="true" aria-controls="panel-1" id="tab-1">General</button>
  <button role="tab" aria-selected="false" aria-controls="panel-2" id="tab-2" tabindex="-1">Privacy</button>
</div>
<div role="tabpanel" id="panel-1" aria-labelledby="tab-1">...</div>
<div role="tabpanel" id="panel-2" aria-labelledby="tab-2" hidden>...</div>
```
**Keyboard:** Arrow keys switch tabs. Tab moves into panel. Home/End go to first/last tab.

### Menu
```html
<button aria-haspopup="true" aria-expanded="false" aria-controls="menu-1">Options</button>
<ul role="menu" id="menu-1" hidden>
  <li role="menuitem">Edit</li>
  <li role="menuitem">Delete</li>
  <li role="menuitem">Share</li>
</ul>
```
**Keyboard:** Enter/Space opens menu. Arrow keys navigate items. Escape closes. Type-ahead supported.

### Accordion
```html
<h3>
  <button aria-expanded="true" aria-controls="section-1">Section Title</button>
</h3>
<div id="section-1" role="region" aria-labelledby="accordion-btn-1">
  <p>Section content...</p>
</div>
```
**Keyboard:** Enter/Space toggles. Optionally: arrow keys between headers, Home/End.

### Alert and Status Messages
```html
<!-- Alert: important, time-sensitive -->
<div role="alert">Form submission failed. Please correct errors.</div>

<!-- Status: advisory, not urgent -->
<div role="status">3 results found.</div>

<!-- Live region: custom updates -->
<div aria-live="polite" aria-atomic="true">Cart: 5 items</div>
```

### Tooltip
```html
<button aria-describedby="tooltip-1">Save</button>
<div role="tooltip" id="tooltip-1">Save your progress (Ctrl+S)</div>
```
**Keyboard:** Shows on focus, hides on Escape. Not interactive.

## Live Regions

Announce dynamic content changes to screen readers.

| Attribute | Value | Behavior |
|-----------|-------|----------|
| `aria-live` | `polite` | Announced after current speech finishes |
| `aria-live` | `assertive` | Interrupts current speech (use sparingly) |
| `aria-atomic` | `true` | Announce entire region, not just change |
| `aria-relevant` | `additions text` | What changes to announce (default) |

### Implicit Live Regions
- `role="alert"` = `aria-live="assertive"`
- `role="status"` = `aria-live="polite"`
- `role="log"` = `aria-live="polite"` (additions only)
- `role="timer"` = no default live (too noisy)

## States and Properties

### Common States
| Attribute | Purpose | Values |
|-----------|---------|--------|
| `aria-expanded` | Expandable control state | `true` / `false` |
| `aria-selected` | Selection state (tabs, listbox) | `true` / `false` |
| `aria-checked` | Check state (checkbox, switch) | `true` / `false` / `mixed` |
| `aria-pressed` | Toggle button state | `true` / `false` / `mixed` |
| `aria-disabled` | Disabled state | `true` / `false` |
| `aria-hidden` | Hidden from AT | `true` / `false` |
| `aria-invalid` | Validation state | `true` / `false` / `grammar` / `spelling` |
| `aria-busy` | Loading state | `true` / `false` |
| `aria-current` | Current item indicator | `page` / `step` / `date` / `true` |

### Common Properties
| Attribute | Purpose |
|-----------|---------|
| `aria-label` | Accessible name (string) |
| `aria-labelledby` | Accessible name (ID reference) |
| `aria-describedby` | Accessible description (ID reference) |
| `aria-controls` | ID of controlled element |
| `aria-owns` | ID of owned elements (virtual parent) |
| `aria-haspopup` | Indicates popup type (`menu`, `dialog`, etc.) |
| `aria-required` | Required form field |
| `aria-errormessage` | ID of error message element |
| `aria-keyshortcuts` | Keyboard shortcuts for element |

## Keyboard Interaction Patterns

### General
- **Tab/Shift+Tab** — Move between focusable elements
- **Enter/Space** — Activate buttons, links, checkboxes
- **Escape** — Close overlays, cancel operations
- **Arrow keys** — Navigate within composite widgets (tabs, menus, grids)

### Focus Management
- Use `tabindex="0"` to make non-interactive elements focusable
- Use `tabindex="-1"` for programmatically focusable elements (not in tab order)
- Never use `tabindex` > 0
- Manage roving tabindex within composite widgets (one child at tabindex="0", rest at "-1")

### Skip Navigation
```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<!-- ...site header and nav... -->
<main id="main-content">...</main>
```
```css
.skip-link {
  position: absolute;
  left: -9999px;
}
.skip-link:focus {
  left: 0;
  top: 0;
  z-index: 9999;
}
```

## Hiding Content

| Method | Visible | In AT | In Focus Order |
|--------|---------|-------|----------------|
| `display: none` | No | No | No |
| `visibility: hidden` | No | No | No |
| `aria-hidden="true"` | Yes | No | Yes (bug!) |
| `.sr-only` (clip) | No | Yes | Yes |
| `hidden` attribute | No | No | No |

### Screen Reader Only (Visually Hidden)
```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```
