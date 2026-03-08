# Design Evaluation Checklist

Systematic checklist for comprehensive UX/UI review. Covers all critical dimensions from Norman's usability principles and universal design laws.

## Usability Foundations

### Discoverability
- [ ] Primary actions are immediately visible without scrolling
- [ ] Interactive elements are distinguishable from static content
- [ ] Navigation structure is clear within 5 seconds of viewing
- [ ] No hidden functionality without a discoverable entry point
- [ ] New features have visible entry points (not just buried in menus)
- [ ] Empty states guide users to their first action

### Feedback
- [ ] Every tap/click produces immediate visual response (<100ms)
- [ ] Loading states shown for operations >1 second
- [ ] Success confirmations for completed actions
- [ ] Error states clearly explain the problem and solution
- [ ] Progress indicators for multi-step processes
- [ ] System status always visible (connection, sync, mode)

### Conceptual Model
- [ ] Interface metaphors are consistent throughout
- [ ] Similar functions work the same way everywhere
- [ ] Terminology is consistent (don't mix "delete"/"remove"/"trash")
- [ ] User can predict what will happen before acting
- [ ] Mental model matches actual system behavior
- [ ] New concepts are introduced with familiar analogies

### Affordances and Signifiers
- [ ] Buttons look tappable (raised, colored, distinct from text)
- [ ] Text links are visually distinct from plain text
- [ ] Draggable elements have grab handles
- [ ] Scrollable areas indicate more content (partial items, scroll indicators)
- [ ] Disabled elements appear disabled (grayed out, reduced opacity)
- [ ] Swipeable items hint at hidden actions

### Mapping
- [ ] Controls are spatially close to what they affect
- [ ] Left/right controls map to left/right outcomes
- [ ] Up = increase, down = decrease
- [ ] Color coding matches cultural conventions (red=danger, green=success)
- [ ] Toggle states clearly show on/off
- [ ] Back navigation returns to expected previous state

### Constraints
- [ ] Invalid actions are prevented, not just punished
- [ ] Required fields are marked before submission
- [ ] Input fields restrict to valid characters/formats
- [ ] Destructive actions require additional confirmation
- [ ] Date pickers prevent invalid date selections
- [ ] Form progression disabled until prerequisites met

## Cognitive Load

### Information Architecture
- [ ] Content grouped by user mental model (not system structure)
- [ ] Navigation labels use user language (not internal jargon)
- [ ] Maximum 7±2 top-level navigation items
- [ ] Hierarchy depth ≤4 levels without search alternative
- [ ] Related features are co-located
- [ ] Most common tasks have the shortest paths

### Chunking and Organization
- [ ] Long lists grouped into categories with headers
- [ ] Forms divided into logical sections
- [ ] Numbers formatted with separators (1,234,567)
- [ ] Content uses headings, lists, and whitespace for scanning
- [ ] No wall-of-text — paragraphs ≤3-4 lines on mobile

### Progressive Disclosure
- [ ] Advanced options hidden behind "More" or expandable sections
- [ ] Settings organized by frequency of use
- [ ] First-run experience shows essentials only
- [ ] Details available on demand (expand/detail view)
- [ ] Complexity increases gradually as user progresses

### Decision Simplification
- [ ] One primary CTA per screen (Von Restorff Effect)
- [ ] Smart defaults for all settings (80/20 rule)
- [ ] Recommendations or "popular" labels reduce choice anxiety
- [ ] Binary choices use toggles, not dropdowns
- [ ] Search available for lists >10-15 items

## Visual Design

### Hierarchy
- [ ] Clear visual hierarchy (primary > secondary > tertiary actions)
- [ ] Heading sizes decrease consistently with level
- [ ] Most important content has highest contrast
- [ ] Whitespace separates distinct content groups
- [ ] Eye flow follows F-pattern (text) or Z-pattern (marketing)

### Typography
- [ ] Body text ≥16px web / 17pt iOS / 16sp Android
- [ ] Line height ≥1.4x for body text
- [ ] Line length 45-75 characters
- [ ] Maximum 2 typefaces in the interface
- [ ] Sufficient weight contrast between hierarchy levels
- [ ] No text over busy backgrounds without overlay

### Color
- [ ] Color contrast ≥4.5:1 for body text (WCAG AA)
- [ ] Color not used as sole indicator of meaning
- [ ] Consistent semantic colors (error=red, success=green)
- [ ] Maximum 3-5 colors plus neutrals
- [ ] Dark mode tested and functional
- [ ] Color palette works for common colorblindness types

### Layout and Spacing
- [ ] Consistent spacing system throughout (4px or 8px base)
- [ ] Alignment on clear grid lines
- [ ] Adequate padding inside containers (≥12px)
- [ ] Sufficient spacing between tap targets (≥8px)
- [ ] Responsive layout adapts gracefully across screen sizes
- [ ] No horizontal scrolling on primary content

### Icons
- [ ] Consistent icon style (all outline or all filled)
- [ ] Navigation icons paired with text labels
- [ ] Icons recognizable at smallest display size
- [ ] Standard metaphors used (gear=settings, etc.)
- [ ] Sufficient contrast against background

## Interaction Design

### Touch and Input
- [ ] Touch targets ≥44x44pt (iOS) / 48x48dp (Android)
- [ ] Primary actions within thumb-reachable zone
- [ ] Appropriate keyboard types for each field
- [ ] Autocomplete and suggestions for text fields
- [ ] Clear/reset buttons for search and input fields
- [ ] Paste support for relevant fields

### Navigation
- [ ] Current location always indicated
- [ ] Back navigation available from every screen
- [ ] Deep links restore correct navigation context
- [ ] Tab bar/navigation bar persistent across main screens
- [ ] Gesture navigation doesn't conflict with system gestures
- [ ] No dead ends (every screen has a path forward or back)

### Forms
- [ ] Single-column layout on mobile
- [ ] Labels above or beside fields (not as placeholders only)
- [ ] Inline validation on field blur
- [ ] Error messages below specific fields (not just at top)
- [ ] Field state on error preserved (don't clear valid entries)
- [ ] Smart defaults and auto-fill where possible
- [ ] Keyboard dismissal method clear
- [ ] Submit button states: default, loading, success, error

### Error Handling
- [ ] Error messages in plain language (no codes)
- [ ] Error messages suggest specific corrective action
- [ ] Undo available for destructive actions
- [ ] Drafts auto-saved regularly
- [ ] Network errors have retry option
- [ ] Offline state clearly communicated with available actions

### Animation and Transitions
- [ ] Transitions between screens are smooth (250-350ms)
- [ ] Button press feedback is immediate (<100ms)
- [ ] Animations serve a purpose (orientation, feedback, status)
- [ ] No animation blocks user interaction
- [ ] Reduced-motion preference respected
- [ ] Loading skeletons used instead of blank screens

## Accessibility

### Perceivable
- [ ] Text resizable to 200% without content loss
- [ ] All images have alt text / accessibility labels
- [ ] Video has captions/subtitles
- [ ] Audio content has text alternative
- [ ] Content readable without color
- [ ] No flashing content (>3 flashes per second)

### Operable
- [ ] All functions keyboard-accessible
- [ ] Focus order logical and predictable
- [ ] Focus indicators visible
- [ ] No time limits without extension option
- [ ] Touch targets meet minimum size
- [ ] Complex gestures have simple alternatives

### Understandable
- [ ] Language is clear and concise
- [ ] Consistent navigation across screens
- [ ] Error identification and correction guidance
- [ ] Help is available in context
- [ ] Predictable behavior (no unexpected context changes)

### Robust
- [ ] Works with screen readers (VoiceOver, TalkBack)
- [ ] Proper semantic structure (headings, lists, landmarks)
- [ ] Dynamic content updates announced to assistive tech
- [ ] Switch control compatible
- [ ] Voice control labels match visible text

## Mobile-Specific

### Performance Perception
- [ ] First meaningful content visible within 1-2 seconds
- [ ] Skeleton screens for content loading
- [ ] Optimistic UI updates for user actions
- [ ] Lazy loading for off-screen content
- [ ] Cached content shown while refreshing

### Device Capabilities
- [ ] Haptic feedback for significant interactions (iOS)
- [ ] Supports both orientations or clearly locks one
- [ ] Safe area insets respected (notch, rounded corners)
- [ ] Pull-to-refresh where contextually appropriate
- [ ] Camera/photo access with clear purpose explanation

### Offline and Connectivity
- [ ] Graceful degradation when offline
- [ ] Queued actions sync when reconnected
- [ ] Offline state clearly indicated
- [ ] Cached content available offline
- [ ] No data loss on connectivity interruption

## Emotional Design

### First Impression
- [ ] Interface aesthetic quality is high (visceral level)
- [ ] Brand identity is immediately recognizable
- [ ] Loading/splash screen is polished
- [ ] Empty states are engaging, not blank

### Ongoing Experience
- [ ] Micro-interactions provide moments of delight
- [ ] Success states celebrate user achievements
- [ ] Tone of copy matches brand personality
- [ ] User feels in control, not frustrated

### Trust and Safety
- [ ] No dark patterns (deceptive UI)
- [ ] Privacy options clearly accessible
- [ ] Destructive actions clearly warned
- [ ] Permission requests explained before appearing
- [ ] User data handling transparent

## Priority Matrix

### Critical (Must Fix Before Release)
- Broken affordances (buttons that don't look clickable)
- Missing feedback (actions with no response)
- Inaccessible content (can't be reached or read)
- Error states with no recovery path
- Touch targets too small
- Text contrast below WCAG AA

### Important (Fix in Next Sprint)
- Inconsistent patterns between screens
- Poor error messages
- Missing loading states
- Suboptimal information hierarchy
- No empty states
- Incomplete dark mode support

### Enhancement (Backlog)
- Animation polish
- Micro-interaction refinements
- Advanced accessibility (AAA compliance)
- Personalization features
- Performance optimization for perceived speed

## Scoring Guide

Rate each category 1-10:

| Score | Meaning |
|-------|---------|
| 1-3 | Fundamental issues. Blocks usability. |
| 4-5 | Below standard. Noticeable friction. |
| 6-7 | Adequate. Meets baseline expectations. |
| 8-9 | Good. Polished and thoughtful. |
| 10 | Exceptional. Best-in-class implementation. |

### Category Weights

| Category | Weight | Rationale |
|----------|--------|-----------|
| Usability Foundations | 30% | Core functionality must work |
| Cognitive Load | 20% | Users must understand the interface |
| Visual Design | 15% | Hierarchy and clarity |
| Interaction Design | 20% | Smooth, intuitive interactions |
| Accessibility | 10% | Inclusive by default |
| Emotional Design | 5% | Polish and delight |

**Overall Score** = Weighted average across categories

## References

- Norman, D. (2013). *The Design of Everyday Things*
- Lidwell et al. (2010). *Universal Principles of Design*: 80/20 Rule, Accessibility, Aesthetic-Usability Effect, Affordance, Alignment, Chunking, Cognitive Dissonance, Color, Comparison, Confirmation, Consistency, Constraint, Entry Point, Errors, Feedback Loop, Fitts' Law, Five Hat Racks, Flexibility-Usability Tradeoff, Forgiveness, Gutenberg Diagram, Hick's Law, Hierarchy, Hierarchy of Needs, Highlighting, Legibility, Mapping, Mental Model, Ockham's Razor, Progressive Disclosure, Proximity, Signal-to-Noise Ratio, Visibility
