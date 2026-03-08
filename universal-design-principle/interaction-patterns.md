# Interaction Patterns

Comprehensive interaction design patterns for mobile, web, and cross-platform interfaces. Synthesizes Norman's principles of action with universal design patterns.

## Navigation Patterns

### Hierarchical Navigation (Drill-Down)
Best for: content-heavy apps with clear categories.

```
Home → Category → Subcategory → Detail
```

- Always show clear back navigation
- Breadcrumbs for 3+ levels (web) or navigation title (mobile)
- Don't exceed 4 levels without search/shortcuts
- Each level should have a clear, scannable list

### Tab-Based Navigation
Best for: 2-5 top-level sections of equal importance.

| Platform | Placement | Max Items |
|----------|-----------|-----------|
| iOS | Bottom bar | 5 (use "More" for overflow) |
| Android | Bottom bar or top tabs | 5 bottom, scrollable top |
| Web | Top horizontal | 7-8 visible, overflow menu |

**Rules:**
- Persistent across the app (don't hide tabs contextually)
- Each tab maintains independent navigation state
- Badge counts for attention-requiring tabs
- Active state must be clearly distinguishable
- Icons + labels (not icons alone) for bottom tabs

### Hub-and-Spoke
Best for: apps with independent task-based sections.

```
        ┌── Task A
Hub ────┼── Task B
        └── Task C
```

- User always returns to hub before switching tasks
- Good for focused workflows (e.g., banking: transfer, pay, invest)
- Each spoke is self-contained
- Clear "done" or "back to home" from each spoke

### Flat Navigation
Best for: simple apps, content browsing, dashboards.
- All screens accessible from a single level
- Swipe between pages or scroll through sections
- Pagination dots or scroll indicators for orientation

### Search-Driven Navigation
Best for: large content catalogs, utility apps.
- Prominent search bar at top
- Recent searches and suggestions
- Filters and facets for refinement
- Results with clear previews

## Input Patterns

### Forms

**Layout Rules:**
- Single column only on mobile
- Top-aligned labels (fastest scanning and completion)
- Group related fields with section headers
- Logical tab order matching visual order
- Required fields clearly marked (or better: mark optional fields)

**Field Design:**
- Appropriate keyboard type for each field (email, phone, number, URL)
- Placeholder text as examples, NOT as labels (disappears on focus)
- Input masks for formatted data (phone, credit card, date)
- Character counters for limited-length fields
- Clear/reset button for text fields

**Validation:**
- Inline validation on blur (not on every keystroke)
- Show success state for valid fields (subtle green check)
- Error messages below the field, not in alerts
- Error text: explain what's wrong AND how to fix it
- Don't clear valid fields when one field has an error
- Scroll to first error and focus it

**Smart Defaults:**
- Pre-fill from user profile, location, or previous entries
- Default to the most common selection
- Remember user's last choice for repeated forms
- Auto-detect format when possible (credit card type from number)

### Selection Controls

| Need | Control | When |
|------|---------|------|
| One of 2-3 | Segmented control | Quick toggle |
| One of 4-7 | Radio buttons / selection list | All visible |
| One of 8+ | Dropdown / picker / search | Too many to display |
| Multiple of few | Checkboxes / chips | All visible |
| Multiple of many | Multi-select with search | Large lists |
| Numeric range | Slider | Approximate values |
| Exact number | Stepper or text field | Precise values |
| Date/time | Date picker | Standard dates |
| Free text | Text field/area | Open-ended input |

### Search

**Progressive Disclosure in Search:**
1. Search icon (collapsed) → reveals search bar on tap
2. As user types → show instant suggestions (autocomplete)
3. On submit → show results with filters
4. On filter → show refined results with active filter chips

**Search Best Practices:**
- Forgive typos: fuzzy matching, "Did you mean...?"
- Scope indicators: what is being searched
- Recent and popular searches as zero-state
- Clear button inside search field
- Voice input option on mobile
- Highlight matching terms in results

## Feedback Patterns

### Immediate Feedback (<100ms)
- Button press states (highlight, ripple, scale)
- Toggle switch animation
- Checkbox check/uncheck
- Pull-to-refresh visual cue

### Short Feedback (100ms - 1s)
- Toast/snackbar for non-critical confirmations
- Inline success/error states
- Like/favorite animations
- Swipe action completion

### Progress Feedback (1s - 10s)
- Determinate progress bar (when duration is known)
- Indeterminate spinner (when duration is unknown)
- Skeleton screens (for content loading)
- Percentage + time estimate for long operations

### Long Operation Feedback (>10s)
- Background processing with notification on completion
- Step-by-step progress ("Uploading... Processing... Almost done...")
- Allow user to continue other tasks
- Resume capability if interrupted

### Feedback Hierarchy

| Severity | Pattern | Duration | Example |
|----------|---------|----------|---------|
| Success | Toast/snackbar | 3-4 seconds, auto-dismiss | "Message sent" |
| Info | Inline banner | Until dismissed | "New version available" |
| Warning | Persistent banner | Until resolved | "Low storage" |
| Error | Inline error + red border | Until fixed | Form validation error |
| Critical | Modal dialog | Until acknowledged | Data loss warning |

## Error Handling Patterns

### Prevention First (Constraints)
- Disable invalid actions (gray out, don't hide)
- Input masks prevent formatting errors
- Confirmation for destructive actions
- Type-appropriate keyboards on mobile
- Limit input ranges (min/max on number fields)

### Graceful Recovery
- **Undo** > Confirmation dialogs (faster, less disruptive)
- Auto-save drafts at regular intervals
- Preserve form state on navigation/errors
- Offline queue actions for retry when connected
- "Try again" button with one tap (not re-entering data)

### Error Message Formula
```
[What happened] + [Why it happened (if known)] + [What to do next]
```

**Examples:**
- Bad: "Error 404"
- Good: "Page not found. This page may have been moved. Try searching or go to the homepage."
- Bad: "Invalid input"
- Good: "Password must be at least 8 characters with one number."

### Empty States
Never show a blank screen. Empty states should:
1. Explain why it's empty
2. Suggest what to do next
3. Provide a clear action button
4. Optional: add illustration for warmth

```
[Illustration]
"No messages yet"
"Start a conversation with your team"
[+ New Message] button
```

## Gesture Patterns (Mobile)

### Standard Gestures and Conventions

| Gesture | Common Use | Rule |
|---------|-----------|------|
| Tap | Select, activate | Primary interaction |
| Long press | Context menu, selection mode | Always have tap alternative |
| Swipe horizontal | Navigation, reveal actions | Show peek of actions |
| Swipe vertical | Scroll, refresh, dismiss | Don't hijack scroll |
| Pinch | Zoom | Standard for media |
| Double tap | Zoom in, like | Not for critical actions |
| Drag | Reorder, move | Show grab handles |

### Gesture Design Rules
1. **Discoverable alternatives**: Every gesture must have a visible button equivalent
2. **Forgiving**: Accidental gestures must be undoable
3. **Standard**: Don't redefine established gesture meanings
4. **Progressive**: Teach gestures through discovery, not upfront tutorials
5. **Escapable**: Any gesture-initiated action can be cancelled mid-gesture

### Swipe Actions (List Items)

**Leading swipe** (left-to-right): Positive/primary actions (archive, pin, mark read)
**Trailing swipe** (right-to-left): Secondary/destructive actions (delete, flag)

- Partial reveal shows preview of actions
- Full swipe triggers primary action
- Different colors signal different action types (green=positive, red=destructive)
- Maximum 3 actions per side

## Transition and Animation Patterns

### Purposeful Animation
Every animation should serve one of these purposes:

| Purpose | Example | Duration |
|---------|---------|----------|
| **Orientation** | Screen transitions, navigation | 250-350ms |
| **Feedback** | Button press, toggle switch | 100-200ms |
| **Status** | Loading spinner, progress bar | Continuous |
| **Delight** | Success celebration, onboarding | 300-500ms |
| **Spatial** | Card expand, drawer slide | 250-400ms |

### Animation Rules
- 200-300ms for most UI transitions (fast enough to feel responsive, slow enough to track)
- Ease-out for entering elements (decelerate into place)
- Ease-in for exiting elements (accelerate away)
- Spring animations for physical-feeling interactions
- Never block user interaction during decorative animation
- Respect reduced-motion accessibility settings

### Transition Types

| From → To | Pattern | Use When |
|-----------|---------|----------|
| List → Detail | Hero/shared element transition | Content continuity |
| Screen → Screen | Slide (push/pop) | Hierarchical navigation |
| Action → Result | Crossfade | Non-spatial relationship |
| Hidden → Visible | Slide up / fade in | Modals, sheets, menus |
| Visible → Hidden | Slide down / fade out | Dismissing overlays |

## Progressive Disclosure

### Layered Complexity

```
Layer 1: Essential    → Always visible (primary actions, key info)
Layer 2: Expected     → One interaction away (secondary actions, details)
Layer 3: Optional     → Behind "Advanced" or "More" (power features, settings)
Layer 4: Specialized  → Deep settings, developer options, bulk operations
```

### Techniques

| Technique | Best For | Example |
|-----------|----------|---------|
| Expandable sections | Optional details | "Show more" / accordion |
| Hover/long-press reveal | Secondary actions | Toolbar on hover |
| Modal/sheet | Focused sub-tasks | Edit profile sheet |
| Staged forms | Multi-step processes | Wizard/stepper |
| Contextual menus | Situational actions | Right-click / long-press menu |
| Inline expansion | Related content | Thread expansion |
| Tabs within content | Alternative views | Map/List/Grid toggle |

### MAYA Principle (Most Advanced Yet Acceptable)
Push innovation only as far as users can accept:
- Introduce one new pattern at a time
- Pair innovation with familiar elements
- Provide migration paths from old to new patterns
- Default to convention, offer innovation as opt-in

## Responsive Patterns

### Layout Adaptation

| Viewport | Strategy | Example |
|----------|----------|---------|
| Mobile (<600px) | Single column, stacked | Full-width cards |
| Tablet (600-1024px) | Two columns, split view | Master-detail |
| Desktop (>1024px) | Multi-column, sidebar | Dashboard with panels |

### Content Priority
- **Mobile first**: Design for smallest screen, then enhance
- **Content priority**: Most important content first, supplementary content below
- **Touch first**: Design for touch, enhance for mouse/keyboard
- **Offline first**: Design for degraded connectivity, enhance when online

### Adaptive Components

| Component | Mobile | Tablet | Desktop |
|-----------|--------|--------|---------|
| Navigation | Bottom tabs | Side rail | Full sidebar |
| Lists | Full width | 2-column grid | Table view |
| Actions | FAB / bottom bar | Inline buttons | Toolbar |
| Modals | Full screen | Center sheet | Side panel |
| Search | Collapsible | Persistent bar | Persistent + filters |

## Accessibility Interaction Patterns

### Keyboard Navigation
- All interactive elements focusable and operable via keyboard
- Logical tab order matching visual order
- Skip navigation links for repeated elements
- Focus indicators visible and high-contrast
- Keyboard shortcuts for frequent actions (with discoverability)

### Screen Reader Patterns
- Semantic HTML/native controls over custom widgets
- Meaningful labels for all interactive elements
- State announcements (expanded/collapsed, selected, loading)
- Live regions for dynamic content updates
- Heading hierarchy for page structure

### Motor Accessibility
- Touch targets ≥44pt minimum
- No time-dependent interactions (or provide extensions)
- Alternatives to complex gestures (pinch, multi-finger)
- Switch control compatibility
- Voice control labels matching visible text

## References

- Norman, D. (2013). *The Design of Everyday Things*, Chapters 3-4
- Lidwell et al. (2010). *Universal Principles of Design*: Affordance, Constraint, Control, Entry Point, Feedback Loop, Fitts' Law, Flexibility-Usability Tradeoff, Forgiveness, Mapping, Progressive Disclosure
