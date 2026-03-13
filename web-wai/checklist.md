# Web Accessibility Audit Checklist

Practical checklist for auditing web content against WCAG 2.2 Level AA.

## Document Structure

- [ ] Page has a descriptive `<title>`
- [ ] `<html>` has correct `lang` attribute
- [ ] Content language changes marked with `lang` attribute
- [ ] Heading hierarchy is logical (h1 > h2 > h3, no skipped levels)
- [ ] One `<h1>` per page (or per sectioning element)
- [ ] Landmark regions used: `<header>`, `<nav>`, `<main>`, `<footer>`
- [ ] One `<main>` element per page
- [ ] Multiple same-type landmarks have distinct labels
- [ ] Lists use `<ul>`, `<ol>`, or `<dl>` appropriately
- [ ] Data tables use `<th>`, `<caption>`, and `scope`

## Images and Media

- [ ] All `<img>` have `alt` attributes
- [ ] Decorative images use `alt=""`
- [ ] Complex images have extended descriptions (aria-describedby or longdesc)
- [ ] SVGs have `role="img"` and accessible name (`<title>` or aria-label)
- [ ] Icon fonts/SVG icons have sr-only text or aria-label
- [ ] Prerecorded video has captions
- [ ] Prerecorded video has audio descriptions
- [ ] Prerecorded audio has text transcript
- [ ] Media players have keyboard-accessible controls
- [ ] Auto-playing media can be paused/stopped

## Color and Contrast

- [ ] Normal text: 4.5:1 contrast ratio
- [ ] Large text (>=18pt or >=14pt bold): 3:1 contrast ratio
- [ ] UI components and borders: 3:1 contrast ratio
- [ ] Information not conveyed by color alone
- [ ] Links distinguishable from surrounding text (underline or 3:1 + non-color indicator)
- [ ] Focus indicators have sufficient contrast
- [ ] Error states not indicated by color alone

## Typography and Layout

- [ ] Text resizable to 200% without loss of content
- [ ] Content reflows at 320px without horizontal scroll
- [ ] Text spacing adjustable (line-height 1.5x, letter 0.12em, word 0.16em, paragraph 2x)
- [ ] No content clipped or overlapping at zoom levels
- [ ] Reading order matches visual order in DOM
- [ ] Content works in portrait and landscape orientation

## Keyboard and Focus

- [ ] All interactive elements reachable via Tab key
- [ ] Focus order is logical and matches visual layout
- [ ] Focus indicator is clearly visible (>=2px, 3:1 contrast)
- [ ] No keyboard traps (can always Tab/Escape out)
- [ ] Skip navigation link present and functional
- [ ] Custom widgets have appropriate keyboard interaction
- [ ] Single-character shortcuts can be remapped or disabled
- [ ] Focus not entirely obscured by sticky headers/footers
- [ ] Drag operations have single-pointer alternative

## Forms

- [ ] Every input has a visible, programmatically associated `<label>`
- [ ] Required fields indicated accessibly (not just color/asterisk)
- [ ] `aria-required="true"` or `required` attribute on required fields
- [ ] Autocomplete attributes set for common user data (name, email, etc.)
- [ ] Fieldsets and legends group related controls
- [ ] Form instructions provided before the form or inline
- [ ] Input purpose identifiable (autocomplete attribute)

## Error Handling

- [ ] Errors described in text (not just color)
- [ ] Error messages linked to their fields (aria-describedby or aria-errormessage)
- [ ] Error messages explain how to fix the problem
- [ ] Form submission errors don't clear valid entries
- [ ] Users can review and correct before final submission
- [ ] Previously entered data not re-requested (redundant entry)

## Navigation

- [ ] Multiple ways to find pages (nav, search, sitemap)
- [ ] Consistent navigation position across pages
- [ ] Consistent labeling of same-function components
- [ ] Breadcrumbs or current-page indicator provided
- [ ] Links have descriptive text (no "click here" or "read more" alone)
- [ ] Links that open new windows/tabs indicate this behavior

## Interactive Components

- [ ] Buttons use `<button>` or `<input type="submit">`
- [ ] Links use `<a href>` for navigation
- [ ] Custom widgets have correct ARIA roles, states, properties
- [ ] Expandable content uses `aria-expanded`
- [ ] Modals trap focus and have `aria-modal="true"`
- [ ] Tooltips/popovers dismissible with Escape
- [ ] Hover/focus content stays visible and dismissible
- [ ] Touch targets at least 24x24 CSS pixels

## Dynamic Content

- [ ] Status messages use `role="status"` or `aria-live="polite"`
- [ ] Important alerts use `role="alert"`
- [ ] Loading states communicated (aria-busy, status messages)
- [ ] Content changes don't cause unexpected context changes
- [ ] Infinite scroll has alternative navigation
- [ ] Auto-updating content pausable
- [ ] Animations respect `prefers-reduced-motion`

## Authentication

- [ ] No CAPTCHA or cognitive function test required
- [ ] Alternative auth methods available (passkeys, password managers)
- [ ] Session timeouts warn users and allow extension
- [ ] Data preserved after re-authentication

## Timing

- [ ] Time limits adjustable (turn off, extend 10x, or warn 20 seconds before)
- [ ] Moving/blinking content pausable
- [ ] No content flashes >3 times per second
- [ ] Timeout warnings when data loss possible
- [ ] Non-essential animation can be disabled

## Priority Matrix

| Priority | Categories |
|----------|-----------|
| Critical | Keyboard access, focus management, form labels, image alt text, page title |
| High | Contrast, heading structure, error handling, ARIA on custom widgets |
| Medium | Skip links, landmarks, live regions, text spacing, reflow |
| Low | AAA criteria, enhanced target size, extended descriptions |
