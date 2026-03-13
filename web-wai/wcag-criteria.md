# WCAG 2.2 Success Criteria Reference

Complete success criteria organized by POUR principle and conformance level.

## 1. Perceivable

### Level A
- **1.1.1 Non-text Content** — All non-text content has text alternatives serving equivalent purpose
- **1.2.1 Audio-only/Video-only (Prerecorded)** — Alternatives for prerecorded audio-only and video-only media
- **1.2.2 Captions (Prerecorded)** — Captions for all prerecorded synchronized media audio
- **1.2.3 Audio Description or Media Alternative** — Audio descriptions or text alternative for prerecorded video
- **1.3.1 Info and Relationships** — Structure conveyed through presentation is programmatically determinable
- **1.3.2 Meaningful Sequence** — Reading sequence programmatically determinable when it affects meaning
- **1.3.3 Sensory Characteristics** — Instructions don't rely solely on shape, color, size, location, or sound
- **1.4.1 Use of Color** — Color is not the only visual means of conveying information
- **1.4.2 Audio Control** — Auto-playing audio >3s can be paused/stopped or volume controlled

### Level AA
- **1.2.4 Captions (Live)** — Captions for live audio in synchronized media
- **1.2.5 Audio Description (Prerecorded)** — Audio descriptions for all prerecorded video
- **1.3.4 Orientation** — Content not restricted to single display orientation
- **1.3.5 Identify Input Purpose** — Input field purposes programmatically determinable (autocomplete)
- **1.4.3 Contrast (Minimum)** — Text: 4.5:1 ratio; large text (18pt/14pt bold): 3:1
- **1.4.4 Resize Text** — Text resizable to 200% without loss of content or functionality
- **1.4.5 Images of Text** — Text used instead of images of text (unless essential)
- **1.4.10 Reflow** — Content reflows at 320px width / 256px height without horizontal scrolling
- **1.4.11 Non-text Contrast** — UI components and graphics: 3:1 contrast against adjacent colors
- **1.4.12 Text Spacing** — No content loss when adjusting line-height (1.5x), spacing (2x letter, 1.12x word), paragraph spacing (2x)
- **1.4.13 Content on Hover/Focus** — Hover/focus-triggered content is dismissible, hoverable, and persistent

### Level AAA
- **1.2.6 Sign Language (Prerecorded)** — Sign language for prerecorded audio
- **1.2.7 Extended Audio Description** — Extended audio descriptions when pauses insufficient
- **1.2.8 Media Alternative (Prerecorded)** — Full text alternative for all prerecorded synchronized media
- **1.2.9 Audio-only (Live)** — Text alternative for live audio-only
- **1.3.6 Identify Purpose** — Component purposes programmatically determinable
- **1.4.6 Contrast (Enhanced)** — Text: 7:1 ratio; large text: 4.5:1
- **1.4.7 Low/No Background Audio** — Speech audio: background >=20dB quieter, or no background
- **1.4.8 Visual Presentation** — Customizable colors, width (<=80 chars), spacing, alignment
- **1.4.9 Images of Text (No Exception)** — Images of text only for decoration

## 2. Operable

### Level A
- **2.1.1 Keyboard** — All functionality available via keyboard (no specific timing)
- **2.1.2 No Keyboard Trap** — Keyboard focus can always be moved away from components
- **2.1.4 Character Key Shortcuts** — Single-character shortcuts can be turned off or remapped
- **2.2.1 Timing Adjustable** — Time limits can be turned off, adjusted, or extended (20x)
- **2.2.2 Pause, Stop, Hide** — Moving/blinking/scrolling and auto-updating content pausable
- **2.3.1 Three Flashes or Below Threshold** — No content flashes >3 times/second
- **2.4.1 Bypass Blocks** — Skip mechanism for repeated content blocks
- **2.4.2 Page Titled** — Pages have descriptive, informative titles
- **2.4.3 Focus Order** — Focus order preserves meaning and operability
- **2.4.4 Link Purpose (In Context)** — Link purpose determinable from link text + context
- **2.5.1 Pointer Gestures** — No multipoint or path-based gesture dependency
- **2.5.2 Pointer Cancellation** — Down-event doesn't trigger; activate on up-event with abort/undo
- **2.5.4 Motion Actuation** — Motion-triggered functions have UI alternative; can disable motion

### Level AA
- **2.4.5 Multiple Ways** — Multiple navigation methods to find pages
- **2.4.6 Headings and Labels** — Headings and labels describe topic or purpose
- **2.4.7 Focus Visible** — Keyboard focus indicator is visible
- **2.4.11 Focus Not Obscured (Minimum)** — Focused component not entirely hidden by author-created content
- **2.5.3 Label in Name** — Visible label text included in accessible name
- **2.5.7 Dragging Movements** — Drag operations have single-pointer alternative
- **2.5.8 Target Size (Minimum)** — Touch targets at least 24x24 CSS pixels (or adequately spaced)
- **2.2.6 Timeouts** — Users warned of inactivity timeouts that cause data loss
- **2.3.3 Animation from Interactions** — Non-essential motion animation can be disabled

### Level AAA
- **2.1.3 Keyboard (No Exception)** — All functionality keyboard-operable, no exceptions
- **2.2.3 No Timing** — No time limits at all
- **2.2.4 Interruptions** — Interruptions postponable or suppressible
- **2.2.5 Re-authenticating** — Data preserved after session re-authentication
- **2.3.2 Three Flashes** — No content flashes >3 times/second (absolute)
- **2.4.8 Location** — User's location within page set indicated
- **2.4.9 Link Purpose (Link Only)** — Link purpose from link text alone
- **2.4.10 Section Headings** — Content organized with section headings
- **2.4.12 Focus Not Obscured (Enhanced)** — Focused component fully visible
- **2.4.13 Focus Appearance** — Focus indicator: >=2px thick, >=3:1 contrast change
- **2.5.5 Target Size (Enhanced)** — Touch targets at least 44x44 CSS pixels
- **2.5.6 Concurrent Input Mechanisms** — Multiple input modalities work simultaneously

## 3. Understandable

### Level A
- **3.1.1 Language of Page** — Default language programmatically determinable
- **3.2.1 On Focus** — No context change on focus
- **3.2.2 On Input** — No unexpected context change on input
- **3.3.1 Error Identification** — Errors detected and described in text
- **3.3.2 Labels or Instructions** — Labels/instructions provided for user input

### Level AA
- **3.1.2 Language of Parts** — Language of content parts programmatically determinable
- **3.2.3 Consistent Navigation** — Repeated navigation consistent across pages
- **3.2.4 Consistent Identification** — Same-function components identified consistently
- **3.3.3 Error Suggestion** — Correction suggestions provided when errors detected
- **3.3.4 Error Prevention (Legal/Financial)** — Submissions reversible, checked, or confirmed
- **3.3.7 Redundant Entry** — No re-entry of previously provided information
- **3.3.8 Accessible Authentication (Minimum)** — No cognitive function test for auth (unless alternative provided)

### Level AAA
- **3.1.3 Unusual Words** — Definitions for jargon and idioms
- **3.1.4 Abbreviations** — Expanded forms for abbreviations
- **3.1.5 Reading Level** — Simplified version when text exceeds lower secondary level
- **3.1.6 Pronunciation** — Pronunciation for ambiguous words
- **3.2.5 Change on Request** — Context changes only by user request
- **3.2.6 Consistent Help** — Help mechanisms in consistent location
- **3.3.5 Help** — Context-sensitive help available
- **3.3.6 Error Prevention (All)** — All submissions reversible, checked, or confirmed
- **3.3.9 Accessible Authentication (Enhanced)** — No cognitive test or object recognition for auth

## 4. Robust

### Level A
- **4.1.1 Parsing** — Markup well-formed with complete start/end tags, proper nesting, unique IDs
- **4.1.2 Name, Role, Value** — All UI components have accessible name, role, states, properties, values

### Level AA
- **4.1.3 Status Messages** — Status messages programmatically determinable via role or live region

## New in WCAG 2.2

Criteria added in 2.2 (not in 2.1):
- 2.4.11 Focus Not Obscured (Minimum) — AA
- 2.4.12 Focus Not Obscured (Enhanced) — AAA
- 2.4.13 Focus Appearance — AAA
- 2.5.7 Dragging Movements — AA
- 2.5.8 Target Size (Minimum) — AA
- 3.2.6 Consistent Help — AAA
- 3.3.7 Redundant Entry — AA
- 3.3.8 Accessible Authentication (Minimum) — AA
- 3.3.9 Accessible Authentication (Enhanced) — AAA
- 2.2.6 Timeouts — AA

## Contrast Quick Reference

| Element | AA Ratio | AAA Ratio |
|---------|----------|-----------|
| Normal text (<18pt) | 4.5:1 | 7:1 |
| Large text (>=18pt or >=14pt bold) | 3:1 | 4.5:1 |
| UI components & graphics | 3:1 | — |
| Focus indicator contrast change | 3:1 | — |
