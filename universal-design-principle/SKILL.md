---
name: universal-design-principle
description: Universal design principles for UX, UI, and mobile design. Synthesizes Don Norman's Design of Everyday Things and Lidwell/Holden/Butler's Universal Principles of Design. Use when designing interfaces, reviewing UX/UI, planning user flows, evaluating usability, or making design decisions for any platform.
allowed-tools: [Read, Write, Edit, Glob, Grep, AskUserQuestion]
---

# Universal Design Principles

Comprehensive design guidance synthesizing foundational principles from *The Design of Everyday Things* (Don Norman) and *Universal Principles of Design* (Lidwell, Holden, Butler). Applies to UX, UI, mobile, web, and any human-facing interface design.

## When This Skill Activates

Use this skill when the user:
- Designs or reviews UI/UX for any platform (mobile, web, desktop)
- Plans user flows, navigation, or interaction patterns
- Evaluates usability or accessibility of an interface
- Asks about design principles, patterns, or best practices
- Needs to justify or critique design decisions
- Builds wireframes, prototypes, or design specifications
- Wants to improve learnability, discoverability, or user satisfaction
- Reviews mobile app screens for usability issues
- Asks about cognitive load, mental models, or user psychology

## Core Framework: The Seven Principles

Apply these seven foundational principles (Norman) to every design decision:

### 1. Discoverability
Can the user figure out what actions are possible and how to perform them?
- Make available actions visible
- Provide clear signifiers for all interactive elements
- Avoid hidden gestures without discoverable alternatives

### 2. Feedback
Does the system communicate what is happening?
- Immediate, informative feedback for every action
- Visual, auditory, or haptic confirmation
- Progress indicators for operations >1 second
- Error states must explain what happened and how to recover

### 3. Conceptual Model
Does the user understand how the system works?
- System image must communicate the designer's mental model
- Use familiar metaphors and conventions
- Consistent behavior builds accurate mental models
- When the model breaks, users blame themselves — fix the design

### 4. Affordances
Does the design suggest how elements should be used?
- Buttons should look pressable, sliders should look draggable
- Physical and perceived affordances must align
- Anti-affordances prevent incorrect actions (e.g., grayed-out disabled buttons)

### 5. Signifiers
Do visual/audible cues indicate where and how to act?
- Labels, icons, placeholder text, tooltips
- Signifiers > affordances in importance for digital UI
- Consistent placement teaches users where to look
- When affordance is ambiguous, add an explicit signifier

### 6. Mapping
Is the relationship between controls and outcomes natural?
- Spatial correspondence (left button controls left item)
- Cultural conventions (red = stop/danger, green = go/success)
- Temporal ordering (steps flow left-to-right or top-to-bottom)
- Best mapping: controls physically resemble or adjoin what they affect

### 7. Constraints
Does the design prevent errors through limiting choices?
- Physical constraints (connector only fits one way)
- Logical constraints (graying out invalid options)
- Semantic constraints (red means stop)
- Cultural constraints (established conventions)

## Design Review Process

### 1. Identify Scope and Context

Determine:
- **Platform**: iOS, Android, web, desktop, cross-platform?
- **Users**: Novice, expert, or mixed audience?
- **Task type**: Frequent repetitive tasks vs. occasional complex tasks?
- **Constraints**: Accessibility requirements, device limitations?

### 2. Load Reference Materials

Before starting a deep review, read these supporting files in `.claude/skills/universal-design-principle/`:

- **cognitive-principles.md** — Psychology of users: attention, memory, perception, decision-making
- **interaction-patterns.md** — UI patterns, mobile patterns, navigation, input, and error handling
- **visual-design.md** — Layout, typography, color, hierarchy, Gestalt principles
- **evaluation-checklist.md** — Systematic checklist for comprehensive design review

### 3. Apply the Evaluation Framework

**Layer 1 — Usability Foundations**
- Can users accomplish their primary task without help?
- Are errors recoverable? (Forgiveness principle)
- Is the interface learnable within minutes?
- Does it follow platform conventions?

**Layer 2 — Cognitive Load**
- Is information chunked appropriately? (7±2 rule / 4-chunk modern)
- Does progressive disclosure hide complexity?
- Are choices limited to reduce decision paralysis? (Hick's Law)
- Is recognition favored over recall?

**Layer 3 — Visual & Interaction Design**
- Does visual hierarchy guide the eye? (Gutenberg Diagram, F-pattern)
- Are interactive elements within thumb reach on mobile? (Fitts's Law)
- Is there consistent alignment and spacing?
- Do animations serve a purpose (orientation, feedback, delight)?

**Layer 4 — Emotional & Aesthetic**
- Does the aesthetic support usability? (Aesthetic-Usability Effect: attractive things are perceived as easier to use)
- Is the tone appropriate for the context?
- Are there moments of delight without sacrificing clarity?

### 4. Output Format

Present findings in this structure:

#### Design Assessment: [Screen/Feature Name]

**Context**: [Platform, user type, task type]

##### Strengths
- [Well-implemented patterns with principle references]

##### Issues Found

**[Severity]: [Location]** — [Description]
- **Principle violated**: [Which principle]
- **Impact**: [How this affects users]
- **Recommendation**: [Specific fix with rationale]

##### Design Score

| Category | Score | Notes |
|----------|-------|-------|
| Discoverability | X/10 | |
| Feedback | X/10 | |
| Mental Model | X/10 | |
| Visual Hierarchy | X/10 | |
| Error Prevention | X/10 | |
| **Overall** | **X/10** | |

##### Priority Recommendations
1. **Critical**: [Must-fix issues]
2. **Important**: [Should-fix issues]
3. **Enhancement**: [Nice-to-have improvements]

## Quick Decision Guides

### Navigation Pattern Selection

```
How many top-level sections?
├── 2-5 sections → Tab Bar (mobile) / Top Nav (web)
├── 6-10 sections → Hamburger + Tab Bar hybrid
├── Deep hierarchy → Drill-down navigation
└── Flat content → Scrollable single page
```

### When to Use a Modal vs. Inline

```
Is the action destructive or irreversible?
├── Yes → Modal with confirmation
└── No → Continue
    Does it require focused attention?
    ├── Yes → Modal or dedicated screen
    └── No → Inline / expandable section
```

### Information Density

```
User expertise level?
├── Novice → Progressive disclosure, generous whitespace
├── Intermediate → Balanced density, expandable sections
└── Expert → Dense displays, keyboard shortcuts, customizable
```

## Key Laws and Their Application

| Law | Definition | UI Application |
|-----|-----------|----------------|
| **Fitts's Law** | Time to target = f(distance, size) | Make tap targets ≥44pt; place primary actions within thumb zone |
| **Hick's Law** | Decision time increases with number of choices | Limit options; use progressive disclosure; smart defaults |
| **Miller's Law** | Working memory holds ~4 chunks | Group related items; chunk navigation; limit visible options |
| **Jakob's Law** | Users expect your site to work like others they know | Follow platform conventions; innovate cautiously |
| **Aesthetic-Usability** | Attractive designs are perceived as more usable | Invest in visual polish — it directly improves perceived usability |
| **Von Restorff Effect** | Distinctive items are more memorable | Make primary CTAs visually distinct from secondary actions |
| **Serial Position** | First and last items are recalled best | Place important items at beginning and end of lists |
| **Proximity** | Nearby elements are perceived as related | Group related controls; separate unrelated ones |
| **Tesler's Law** | Every system has irreducible complexity | Absorb complexity in the system so users don't have to |

## Mobile-Specific Guidelines

### Touch Targets
- Minimum 44x44pt (Apple HIG) / 48x48dp (Material)
- 8pt minimum spacing between targets
- Place destructive actions away from common tap zones

### Thumb Zone (One-Handed Use)
- Primary actions in bottom third of screen
- Navigation at bottom (iOS) or top (Android convention)
- Avoid critical actions in top-left corner (hardest to reach)

### Gesture Design
- Every gesture must have a visible alternative
- Swipe actions need discoverable entry points
- Don't override system gestures (swipe-back, pull-to-refresh)
- Progressive: tap first, gesture as shortcut for power users

### Mobile Forms
- One column layout only
- Large input fields with appropriate keyboard types
- Inline validation with clear error messages
- Auto-advance between fields where appropriate
- Show/hide password toggle
- Smart defaults reduce typing

## Anti-Patterns to Avoid

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| Mystery meat navigation | Icons without labels | Add text labels or tooltips |
| Confirmation fatigue | Too many "Are you sure?" dialogs | Use undo instead of confirmation |
| Feature creep | Overwhelming options | 80/20 rule: focus on top 20% of features |
| Learned helplessness | User gives up after repeated failures | Better error messages + guidance |
| Horror vacui | Fear of empty space leading to clutter | Whitespace improves comprehension |
| Dark patterns | Manipulative UI that tricks users | Align business goals with user goals |
| Invisible system status | No feedback during operations | Always show what's happening |
| Ambiguous CTAs | "Submit", "OK", "Click Here" | Use verb + noun: "Save Changes", "Delete Account" |

## References

- Norman, D. (2013). *The Design of Everyday Things: Revised and Expanded Edition*
- Lidwell, W., Holden, K., & Butler, J. (2010). *Universal Principles of Design*
- Supporting files in `.claude/skills/universal-design-principle/`
