---
name: web-wai
description: W3C WAI web accessibility review and implementation guidance based on WCAG 2.2, WAI-ARIA, ATAG, and UAAG standards. Use when building, reviewing, or auditing web content for accessibility, or when the user mentions accessibility, a11y, WCAG, ARIA, screen readers, or assistive technology.
allowed-tools: [Read, Write, Edit, Glob, Grep, Bash]
---

# W3C WAI Web Accessibility

Comprehensive web accessibility skill based on the W3C Web Accessibility Initiative (WAI) standards. Ensures web content is perceivable, operable, understandable, and robust for all users, including those using assistive technologies.

## When This Skill Activates

Use this skill when the user:
- Builds or reviews web UI (HTML, CSS, JS, React, Vue, Svelte, etc.)
- Asks about accessibility, a11y, WCAG, or ARIA
- Wants an accessibility audit or review
- Implements forms, navigation, modals, or interactive widgets
- Works with images, video, audio, or dynamic content
- Mentions screen readers, keyboard navigation, or assistive technology
- Needs accessible color contrast or text sizing guidance

## Core Standards

| Standard | Version | Scope |
|----------|---------|-------|
| **WCAG** | 2.2 | Web content — developers and designers |
| **WAI-ARIA** | 1.2 | Dynamic content semantics for assistive tech |
| **ATAG** | 2.0 | Authoring tools producing accessible output |
| **UAAG** | 2.0 | Browsers and media players |

## The POUR Principles

All web content must be:

1. **Perceivable** — Users can perceive content through available senses
2. **Operable** — Users can navigate and interact with all functionality
3. **Understandable** — Content and UI are clear and predictable
4. **Robust** — Content works with current and future assistive technologies

## Conformance Levels

- **Level A** — Minimum accessibility (must satisfy)
- **Level AA** — Standard target for most projects (legally required in many jurisdictions)
- **Level AAA** — Enhanced accessibility (aim for where feasible)

**Default target: Level AA conformance** unless the user specifies otherwise.

## Review Process

### 1. Determine Scope

- Identify which pages, components, or features to review
- Confirm target conformance level (default: AA)
- Note the tech stack (HTML, React, Vue, etc.)

### 2. Load Reference Materials

Before starting, consult these references in `.claude/skills/web-wai/`:

- **wcag-criteria.md** — Full WCAG 2.2 success criteria by principle and level
- **aria-practices.md** — WAI-ARIA roles, patterns, and keyboard interaction
- **checklist.md** — Practical audit checklist organized by category
- **patterns.md** — Code patterns and anti-patterns with examples

### 3. Review Categories

Apply these checks in order of impact:

**Structural Semantics:**
- Proper heading hierarchy (h1-h6)
- Landmark regions (header, nav, main, footer)
- Lists, tables, and form markup
- Language attributes (lang on html, xml:lang for parts)

**Keyboard & Focus:**
- All interactive elements reachable by keyboard
- Visible focus indicator
- Logical focus order (tabindex management)
- No keyboard traps
- Skip navigation links

**Text Alternatives:**
- Alt text on images (decorative images: alt="")
- Captions and transcripts for media
- Labels for form controls
- Accessible names for all interactive elements

**Color & Contrast:**
- Text contrast minimum 4.5:1 (3:1 for large text)
- Non-text UI contrast minimum 3:1
- Information not conveyed by color alone

**Dynamic Content:**
- ARIA roles, states, and properties on custom widgets
- Live regions for dynamic updates (aria-live)
- Status messages programmatically determinable
- Animation respects prefers-reduced-motion

**Forms & Errors:**
- Labels programmatically associated with inputs
- Error messages descriptive and linked to fields
- Required fields indicated accessibly
- Autocomplete attributes for user data

### 4. Output Format

Present findings in this structure:

#### Accessibility Score: X/10

**Target Level:** AA | **Criteria Checked:** N

#### Passed
- [List well-implemented accessibility features]

#### Issues Found

**[WCAG Criterion]: [File:Line]** — [Priority: Critical/Major/Minor]
```html
<!-- Current -->
<problematic code>

<!-- Fix -->
<accessible code>

<!-- Why: explanation referencing WCAG criterion -->
```

#### Recommendations

1. **Critical** — Must fix (blocks access for some users)
2. **Major** — Should fix (degrades experience significantly)
3. **Minor** — Nice to fix (improves quality)

#### Quick Wins
List 3-5 easy fixes with highest accessibility impact.

## Key Rules

### First Rule of ARIA
If you can use a native HTML element with the semantics and behavior you need, use it instead of adding ARIA. Native elements have built-in keyboard handling, focus management, and assistive technology support.

### Essential Seven
1. Every page needs a descriptive `<title>`
2. Every image needs appropriate alt text
3. Every form input needs a `<label>`
4. Every page needs a `<main>` landmark
5. Every interactive element must be keyboard accessible
6. Color must never be the only indicator
7. Text contrast must meet minimum ratios

## References

- [W3C WAI Fundamentals](https://www.w3.org/WAI/fundamentals/)
- [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
- [WAI Standards Overview](https://www.w3.org/WAI/standards-guidelines/)
