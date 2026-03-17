---
name: ux-ui-pro
description: Professional UI/UX design intelligence for building visually polished, accessible, production-ready interfaces. Covers 67 UI styles, color palettes, typography pairings, layout patterns, accessibility rules, animation timing, forms, navigation, charts, and design system generation. Use when designing pages, choosing colors/fonts, reviewing UI code, or building components. Inspired by UI UX Pro Max (MIT, nextlevelbuilder).
allowed-tools: [Read, Write, Edit, Glob, Grep, AskUserQuestion]
---

# UX UI Pro — Design Intelligence

Professional UI/UX design intelligence for building visually polished, accessible, production-ready interfaces. Applies to SwiftUI, UIKit, React, web, and any visual UI work.

Inspired by [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) (MIT License, Next Level Builder) — adapted and restructured for Apple platform development workflows.

## When This Skill Activates

Use this skill when the user:
- Designs a **page, screen, or view** (landing, dashboard, settings, onboarding, detail)
- Creates or styles **UI components** (buttons, cards, forms, modals, lists, charts)
- Chooses **colors**, **typography**, or **spacing**
- Asks about **UI styles** (glassmorphism, minimalism, brutalism, neumorphism, etc.)
- Needs a **design system** or **design tokens**
- Reviews UI code for **visual quality** or **polish**
- Implements **responsive layout**, **dark mode**, or **theming**
- Works on **animation** timing, **micro-interactions**, or **transitions**
- Asks about **accessibility** (contrast, touch targets, VoiceOver, Dynamic Type)
- Designs **navigation** patterns or **information architecture**
- Creates **charts**, **data visualizations**, or **dashboards**
- Says things like: "looks off", "color feels wrong", "needs polish", "make it look professional"

## Skip For

- Backend logic, APIs, databases, infrastructure
- Non-visual scripts, algorithms, deployment
- Pure data modeling (no UI)

---

## Priority Rules

Rules are ranked by impact. Always apply higher-priority rules first.

### Priority 1 — Accessibility (CRITICAL)

| Rule | Standard |
|------|----------|
| Color contrast | 4.5:1 for normal text, 3:1 for large text (WCAG AA) |
| Touch targets | 44×44pt minimum (Apple HIG) |
| Keyboard/focus | Full keyboard navigation, visible focus rings |
| Screen readers | Meaningful labels, traits, hints (VoiceOver / accessibility labels) |
| Motion | Respect Reduce Motion; provide non-motion alternatives |
| Dynamic Type | Support all text sizes; never clip or truncate at largest sizes |
| Color independence | Never convey meaning through color alone — use icons, labels, patterns |

### Priority 2 — Touch & Interaction (CRITICAL)

| Rule | Standard |
|------|----------|
| Tap targets | 44×44pt minimum, 8pt spacing between targets |
| Loading feedback | Show activity indicator within 100ms of user action |
| Error states | Inline validation, clear error messages, recovery path |
| Haptic feedback | Success (notification), warning (notification), selection (impact light) |
| Gesture affordance | Swipe actions need visual hint; avoid hidden-only gestures |
| Responsiveness | UI must respond to input within 100ms (perceived instant) |

### Priority 3 — Performance (HIGH)

| Rule | Standard |
|------|----------|
| Image optimization | Use system SF Symbols, vector assets; compress raster images |
| Lazy loading | Load off-screen content on demand (LazyVStack, LazyHStack) |
| Layout stability | No layout jumps — use placeholder frames, redacted modifiers |
| Animation budget | Keep animations under 16ms/frame (60fps); use Metal for complex effects |
| Memory | Profile with Instruments; avoid retaining large images in memory |

### Priority 4 — Style Selection (HIGH)

Choose a UI style that matches the product type and audience. Maintain consistency across the entire app.

#### Common UI Styles Reference

| Style | Best For | Key Characteristics |
|-------|----------|-------------------|
| **Minimalist** | Productivity, utilities, tools | White space, muted palette, thin type, subtle shadows |
| **Glassmorphism / Liquid Glass** | iOS 26+, modern Apple apps | Translucent layers, blur, `.glassEffect()`, depth |
| **Neumorphism** | Niche/experimental | Soft extruded shapes, low contrast, inner/outer shadows |
| **Brutalism** | Creative, portfolio, editorial | Raw type, high contrast, asymmetric layouts, bold borders |
| **Flat Design** | Enterprise, dashboards, SaaS | Solid colors, no shadows, clear hierarchy, icon-driven |
| **Material / Elevated** | Android-crossover, content apps | Elevation shadows, surface tints, motion choreography |
| **Skeuomorphism** | Games, music, novelty | Realistic textures, shadows mimicking physical objects |
| **Dark Mode (OLED)** | Media, photography, night use | True black (#000), high contrast accents, luminance hierarchy |
| **Vibrant & Bold** | Consumer, social, youth | Saturated gradients, rounded shapes, playful motion |
| **Retro / Vintage** | Food, lifestyle, nostalgia | Serif type, warm palette, textures, muted tones |
| **Aurora UI** | Ambient, wellness, meditation | Gradient meshes, soft glow, organic shapes, gentle motion |
| **Claymorphism** | Playful, onboarding, kids | 3D clay-like elements, pastel colors, rounded everything |
| **Motion-Driven** | Storytelling, presentations | Scroll-linked animation, parallax, choreographed reveals |
| **Accessible / Ethical** | Government, healthcare, education | Maximum contrast, large type, clear labels, no dark patterns |

### Priority 5 — Layout & Responsive (HIGH)

| Rule | Standard |
|------|----------|
| Mobile-first | Design for smallest screen, progressively enhance |
| No horizontal scroll | Content fits viewport width; use vertical scrolling |
| Safe areas | Respect `safeAreaInset`, notch, Dynamic Island, home indicator |
| Grid system | Use consistent spacing grid (4pt/8pt base) |
| Orientation | Support portrait; landscape optional but must not break layout |
| iPad multitasking | Support Split View, Slide Over if targeting iPad |
| Breakpoints | Compact (iPhone), Regular (iPad), use `@Environment(\.horizontalSizeClass)` |

### Priority 6 — Typography & Color (MEDIUM-HIGH)

#### Typography Rules

| Rule | Standard |
|------|----------|
| Base size | 17pt (iOS body), 13pt (macOS body) |
| Line height | 1.4–1.6× font size for body text |
| Type scale | Use system text styles: `.largeTitle`, `.title`, `.headline`, `.body`, `.caption` |
| Max typefaces | 2 per app (1 display + 1 body, or 1 system font throughout) |
| Readability | 45–75 characters per line for body text |
| Weight hierarchy | Use weight (not size alone) to create emphasis: Regular, Medium, Semibold, Bold |

#### Typography Pairing Principles

| Mood | Display Font | Body Font | Use Case |
|------|-------------|-----------|----------|
| Professional | SF Pro Display | SF Pro Text | Business, productivity |
| Editorial | New York | SF Pro Text | Reading, news, blogs |
| Technical | SF Mono | SF Pro Text | Developer tools, code |
| Playful | SF Pro Rounded | SF Pro Text | Kids, casual, games |
| Elegant | New York (Serif) | SF Pro Text | Luxury, fashion |

For cross-platform or custom fonts, consider these Google Fonts pairings:

| Mood | Heading | Body | Use Case |
|------|---------|------|----------|
| Clean Modern | Inter | Inter | SaaS, dashboards |
| Editorial | Playfair Display | Source Sans 3 | Magazines, blogs |
| Friendly | Nunito | Open Sans | Consumer apps |
| Premium | Cormorant Garamond | Lato | Luxury, fashion |
| Technical | JetBrains Mono | IBM Plex Sans | Developer tools |
| Bold Creative | Syne | DM Sans | Agencies, portfolios |
| Warm Organic | Fraunces | Commissioner | Food, lifestyle |
| Minimal | Outfit | Outfit | Startups, landing pages |

#### Color System Rules

| Rule | Standard |
|------|----------|
| Semantic tokens | Define colors by purpose: `primary`, `secondary`, `accent`, `background`, `surface`, `destructive`, `success`, `warning` |
| Dark mode | Every color needs a dark variant; use `Color(.systemBackground)` or asset catalogs with appearances |
| Tint consistency | Primary tint should appear on key actions and navigation; don't scatter accent colors randomly |
| Neutral palette | Background/surface/border colors should be desaturated — warm gray or cool gray family |
| Status colors | Red = destructive/error, Green = success, Yellow/Orange = warning, Blue = info (universal convention) |
| Opacity | Use opacity for layering (0.05–0.15 for surfaces, 0.3–0.6 for overlays), not for making colors "lighter" |

#### Color Palettes by Product Type

| Product Type | Primary | Secondary | Accent | Background |
|-------------|---------|-----------|--------|------------|
| Finance / Banking | #1A365D (navy) | #2D3748 (slate) | #38A169 (green) | #F7FAFC (cool white) |
| Health / Wellness | #276749 (forest) | #4A5568 (gray) | #D69E2E (gold) | #F0FFF4 (mint) |
| Education | #2B6CB0 (blue) | #4A5568 (gray) | #ED8936 (orange) | #EBF8FF (light blue) |
| E-commerce | #E53E3E (red) | #2D3748 (dark) | #D69E2E (gold) | #FFFAF0 (warm white) |
| Social Media | #6B46C1 (purple) | #4A5568 (gray) | #ED64A6 (pink) | #FAF5FF (lavender) |
| Productivity | #3182CE (blue) | #718096 (cool gray) | #48BB78 (green) | #FFFFFF (white) |
| Food & Dining | #C05621 (burnt orange) | #744210 (brown) | #38A169 (green) | #FFFAF0 (cream) |
| Travel | #2C7A7B (teal) | #4A5568 (gray) | #ED8936 (coral) | #E6FFFA (light teal) |
| Entertainment | #D53F8C (magenta) | #2D3748 (dark) | #ECC94B (yellow) | #1A202C (dark bg) |
| Real Estate | #2D3748 (charcoal) | #718096 (gray) | #C8A951 (gold) | #F7FAFC (light) |
| Kids / Family | #6B46C1 (purple) | #3182CE (blue) | #ED8936 (orange) | #FFF5F7 (pink tint) |
| Photography | #1A202C (near black) | #4A5568 (gray) | #FFFFFF (white) | #000000 (true black) |
| News / Media | #1A202C (black) | #E53E3E (red) | #3182CE (blue) | #FFFFFF (white) |
| Music | #6B46C1 (purple) | #1A202C (dark) | #48BB78 (green) | #1A202C (dark bg) |
| Sports | #E53E3E (red) | #2D3748 (dark) | #ECC94B (yellow) | #FFFFFF (white) |
| Vietnamese Culture | #2E3A87 (indigo) | #6C6C70 (gray) | #F4C542 (gold) | #FAF6F0 (warm white) |

### Priority 7 — Animation & Motion (MEDIUM)

| Rule | Standard |
|------|----------|
| Duration | 150–300ms for UI feedback; 300–500ms for transitions; never >500ms for interactive |
| Easing | Use springs for physical motion (`.spring`, `.bouncy`, `.snappy`); linear only for progress |
| Purpose | Every animation must convey meaning — state change, spatial relationship, or feedback |
| Reduce Motion | Check `accessibilityReduceMotion`; replace motion with opacity crossfade |
| Frame budget | 60fps minimum; complex animations at 120fps on ProMotion displays |
| Choreography | Stagger related elements (50–80ms offset); group related movements |
| Micro-interactions | Button press scale (0.95–0.98), toggle snap, pull-to-refresh rubber band |

### Priority 8 — Forms & Input (MEDIUM)

| Rule | Standard |
|------|----------|
| Labels | Always visible (no placeholder-only labels); use `LabeledContent` or floating labels |
| Validation | Inline, real-time (debounced 300ms); show errors below the field |
| Keyboard | Correct keyboard type (`.emailAddress`, `.numberPad`, `.URL`); dismiss on tap outside |
| Auto-fill | Support password auto-fill, contact auto-fill where appropriate |
| Required fields | Mark clearly; don't rely on asterisk alone |
| Error recovery | Focus the first error field, scroll into view, explain how to fix |
| Submission | Disable button during submission; show progress; handle failure gracefully |

### Priority 9 — Navigation (HIGH)

| Rule | Standard |
|------|----------|
| Predictable back | Every screen has a clear back path; never trap the user |
| Tab bar | Max 5 items; use SF Symbols; highlight active tab |
| Deep linking | Support URL schemes and Universal Links for key screens |
| Breadcrumbs | Show path in complex hierarchies (settings, nested categories) |
| Search | Provide search for any list with >20 items |
| State preservation | Maintain scroll position, tab selection, and form state across navigation |
| Onboarding | Max 3–5 screens; skippable; show progress dots; explain value, not features |

### Priority 10 — Charts & Data Visualization (LOW)

| Rule | Standard |
|------|----------|
| Legends | Always include; place near the chart, not in a separate scroll area |
| Tooltips | Show exact values on tap/hover |
| Color coding | Use accessible palette; don't rely on color alone — add patterns or labels |
| Axes | Label axes clearly; use appropriate scale (linear, log) |
| Empty state | Show meaningful empty state, not blank chart |
| Loading | Skeleton or shimmer placeholder while data loads |
| Annotations | Highlight key data points (peaks, anomalies, milestones) |

---

## Design System Generation Workflow

When building a new screen or feature, follow this sequence:

### Step 1 — Analyze Requirements

Identify:
- **Product type** (e.g., finance, health, productivity)
- **Target audience** (demographics, tech literacy, cultural context)
- **UI style** (see style reference above)
- **Platform** (iOS, macOS, watchOS, web, cross-platform)
- **Key screens** (list the views you need to build)

### Step 2 — Define Design Tokens

Create a token hierarchy:

```
Primitive → Semantic → Component

Primitive:   blue500 = #3182CE
Semantic:    primary = blue500
Component:   button-bg-primary = primary
```

**For SwiftUI projects**, define tokens in an asset catalog or `Color` extension:

```swift
extension Color {
    static let primary = Color("Primary")         // Asset catalog
    static let surface = Color("Surface")
    static let destructive = Color("Destructive")
    static let textPrimary = Color(.label)        // System semantic
    static let textSecondary = Color(.secondaryLabel)
}
```

**For SwiftUI + design tokens file:**

```swift
enum DesignTokens {
    enum Spacing {
        static let xs: CGFloat = 4
        static let sm: CGFloat = 8
        static let md: CGFloat = 16
        static let lg: CGFloat = 24
        static let xl: CGFloat = 32
        static let xxl: CGFloat = 48
    }

    enum CornerRadius {
        static let sm: CGFloat = 8
        static let md: CGFloat = 12
        static let lg: CGFloat = 16
        static let xl: CGFloat = 24
        static let full: CGFloat = .infinity  // Capsule
    }

    enum Shadow {
        static let sm = ShadowStyle(color: .black.opacity(0.05), radius: 2, y: 1)
        static let md = ShadowStyle(color: .black.opacity(0.1), radius: 8, y: 4)
        static let lg = ShadowStyle(color: .black.opacity(0.15), radius: 16, y: 8)
    }
}
```

### Step 3 — Apply Style + Color + Typography

1. Select a **UI style** from the reference table
2. Pick a **color palette** matching the product type
3. Choose a **typography pairing** matching the mood
4. Apply consistently across all screens

### Step 4 — Build Components

For each component, specify:
- **Default**, **hover/pressed**, **disabled**, **error**, **loading** states
- **Light** and **dark** mode appearances
- **Accessibility** labels and traits
- **Animation** for state transitions

### Step 5 — Pre-Delivery Checklist

Before shipping any UI, verify:

**Visual Quality**
- [ ] Consistent spacing grid (4pt/8pt)
- [ ] Color tokens used everywhere (no hardcoded hex)
- [ ] Typography uses system text styles or defined scale
- [ ] Icons are SF Symbols or consistent vector set
- [ ] Dark mode tested and polished
- [ ] No orphaned text (single word on a line)

**Interaction**
- [ ] All tap targets ≥ 44×44pt
- [ ] Loading states for all async operations
- [ ] Error states with recovery actions
- [ ] Haptic feedback on key actions
- [ ] Animations respect Reduce Motion

**Accessibility**
- [ ] VoiceOver labels on all interactive elements
- [ ] 4.5:1 contrast ratio on all text
- [ ] Dynamic Type scales correctly at all sizes
- [ ] No information conveyed by color alone
- [ ] Focus order is logical

**Layout**
- [ ] Safe areas respected (notch, Dynamic Island, home indicator)
- [ ] iPad layout adapts gracefully (no stretched iPhone layout)
- [ ] Landscape doesn't break (if supported)
- [ ] Scroll content doesn't clip under navigation bars
- [ ] Empty states designed for all lists

---

## Quick Decision Trees

### Choosing a UI Style

```
What is the product?
├─ Business / Productivity → Minimalist or Flat Design
├─ Consumer / Social → Vibrant & Bold or Material
├─ Creative / Portfolio → Brutalism or Motion-Driven
├─ Health / Wellness → Aurora UI or Minimalist
├─ Kids / Games → Claymorphism or Vibrant
├─ Luxury / Fashion → Minimalist + Serif typography
├─ Developer Tool → Dark Mode + Monospace
├─ Apple-native (iOS 26+) → Liquid Glass (Glassmorphism)
└─ Government / Education → Accessible / Ethical
```

### Choosing Colors

```
What feeling should the app convey?
├─ Trust & Security → Navy + cool neutrals (finance, healthcare)
├─ Energy & Action → Red/orange + dark contrast (sports, social)
├─ Calm & Wellness → Green/teal + warm neutrals (health, meditation)
├─ Creativity → Purple/magenta + dark bg (music, design)
├─ Warmth & Comfort → Orange/brown + cream bg (food, lifestyle)
├─ Authority & News → Black + red accent (media, news)
└─ Playfulness → Multi-color + pastel bg (kids, casual)
```

### Choosing Animation

```
What is happening?
├─ State change (toggle, select) → 150ms, spring
├─ View transition (push, present) → 300ms, spring(response:0.35)
├─ Attention (badge, notification) → Bounce or pulse symbol effect
├─ Loading / progress → Linear, continuous
├─ Celebration → Confetti, 500ms, respect Reduce Motion
├─ Error → Shake (3 cycles, 200ms total)
└─ Deletion → Fade + slide, 250ms
```

---

## References

- Inspired by [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — MIT License, Next Level Builder
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [Laws of UX](https://lawsofux.com)
- Don Norman, *The Design of Everyday Things*
- Lidwell, Holden, Butler, *Universal Principles of Design*
