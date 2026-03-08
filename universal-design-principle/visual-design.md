# Visual Design Principles

Layout, typography, color, hierarchy, and Gestalt principles for interface design. Grounded in universal design principles and perceptual psychology.

## Gestalt Principles of Perception

The brain organizes visual input into meaningful patterns. These are the laws that govern how users perceive your interface.

### Law of Proximity
Elements near each other are perceived as a group.
- Group related controls, labels, and content spatially
- Use whitespace to separate unrelated elements
- Form fields and their labels should be closer to each other than to other fields
- Card layouts work because proximity groups content

### Law of Similarity
Elements that look similar are perceived as related.
- Consistent button styles for same-type actions
- Same icon style throughout the app
- Color-code categories (all "warning" items are yellow)
- Typography consistency: same style = same hierarchy level

### Law of Closure
The brain completes incomplete shapes into recognizable forms.
- Progress indicators (partial circle = loading)
- Card edges extending off-screen imply scrollable content
- Cropped images suggest more content beyond the viewport
- Use to hint at hidden content without explicit labels

### Law of Continuity (Good Continuation)
The eye follows smooth paths and lines naturally.
- Align elements along clear axes
- Lists, timelines, and step indicators follow this naturally
- Misalignment breaks flow and creates confusion
- Curved paths (onboarding flows) feel natural and guided

### Law of Common Fate
Elements moving in the same direction are perceived as grouped.
- Parallax scrolling groups foreground/background layers
- Coordinated animations signal relationship
- Swiping a card group vs. individual items
- Loading animations that pulse together feel unified

### Law of Figure-Ground
The brain separates foreground (figure) from background.
- Modals use overlays to push content to background
- Cards elevate content above the surface (shadow = figure)
- Active/inactive states use contrast to differentiate figure from ground
- Ensure sufficient contrast between figure and ground

### Law of Pragnanz (Simplicity)
The brain prefers the simplest possible interpretation.
- Simple shapes and clean layouts are processed faster
- Reduce visual noise: fewer borders, shadows, decorations
- If an element can be interpreted multiple ways, simplify until it can't
- Icons should be instantly recognizable simple forms

### Law of Common Region
Elements within a boundary are perceived as grouped.
- Cards, containers, bordered sections
- Background color changes to define regions
- Toolbars, navigation bars, content areas
- Subtle backgrounds > heavy borders for grouping

## Visual Hierarchy

### Creating Hierarchy

Order of visual weight (strongest to weakest):

1. **Size**: Larger elements are seen first
2. **Color/Contrast**: High contrast draws attention
3. **Position**: Top-left (LTR) is scanned first
4. **Weight**: Bold text stands out from regular
5. **Spacing**: Isolated elements draw attention
6. **Depth**: Elevated elements (shadows) appear closer

### Reading Patterns

**F-Pattern** (text-heavy pages):
```
████████████████
████████████████
████████████
████████████
████████
████████
```
- Users scan horizontally at top, then vertically down the left
- Place key content in the first two lines
- Left-align important labels and headings
- Best for: articles, search results, email lists

**Z-Pattern** (minimal text, landing pages):
```
1 ──────────► 2
              │
              ▼
3 ◄────────── 4
```
- Eye moves: top-left → top-right → bottom-left → bottom-right
- Place logo top-left, CTA top-right or bottom-right
- Best for: landing pages, hero sections, login screens

**Gutenberg Diagram** (evenly distributed content):
```
Primary     Strong
Optical     Follow
Area        Area
────────────────
Weak        Terminal
Fallow      Area
Area
```
- Primary optical area (top-left): start reading here
- Terminal area (bottom-right): place CTAs here
- Weak fallow area (bottom-left): least attention — avoid critical content here

### Hierarchy in Practice

| Element | Role | Treatment |
|---------|------|-----------|
| Primary heading | Page identity | Largest, boldest |
| Secondary heading | Section identity | Smaller than primary, clear contrast |
| Body text | Content | Comfortable reading size (16-18px web, 17pt iOS) |
| Caption/metadata | Supporting info | Smaller, lighter color |
| Primary CTA | Main action | High contrast, prominent placement |
| Secondary CTA | Alternative action | Lower visual weight than primary |
| Tertiary action | Least important | Text-only or minimal style |

## Typography

### Type Scale and Sizing

| Platform | Body | Minimum | Line Height |
|----------|------|---------|-------------|
| iOS | 17pt | 11pt | 1.2-1.5x |
| Android | 16sp | 12sp | 1.25-1.5x |
| Web | 16-18px | 12px | 1.4-1.6x |

### Typography Rules

1. **Maximum 2 typefaces** per interface (one for headings, one for body — or one for everything)
2. **Minimum contrast ratio**: 4.5:1 for body text, 3:1 for large text (WCAG AA)
3. **Line length**: 45-75 characters per line for body text (optimal: 66)
4. **Paragraph spacing**: 0.5-1.0x the body font size
5. **Letter spacing**: Don't modify default for body text; slight increase for ALL CAPS
6. **Alignment**: Left-align body text (LTR). Center only for short titles/labels
7. **Weight contrast**: Minimum 2 weight steps between hierarchy levels (Regular → Bold, not Regular → Medium)

### Type Hierarchy Recipe

```
Display:    34pt Bold      — Hero text, feature titles
Title 1:    28pt Bold      — Page titles
Title 2:    22pt Semibold  — Section headings
Title 3:    20pt Semibold  — Subsection headings
Headline:   17pt Semibold  — List headers, card titles
Body:       17pt Regular   — Primary content
Callout:    16pt Regular   — Secondary content
Subhead:    15pt Regular   — Supporting text
Footnote:   13pt Regular   — Timestamps, metadata
Caption:    12pt Regular   — Labels, helper text
Caption 2:  11pt Regular   — Fine print (use sparingly)
```

### Legibility Checklist
- [ ] Body text ≥16px (web) / 17pt (iOS) / 16sp (Android)
- [ ] Contrast ratio ≥4.5:1 for normal text
- [ ] Line height ≥1.4x for body text
- [ ] Line length 45-75 characters
- [ ] No justified text on mobile (causes irregular spacing)
- [ ] Key content not conveyed solely through italic or color

## Color

### Functional Color System

| Role | Purpose | Example |
|------|---------|---------|
| **Primary** | Brand identity, primary CTAs | App accent color |
| **Secondary** | Supporting actions, accents | Secondary buttons |
| **Surface** | Backgrounds, cards | White, light gray |
| **On-surface** | Content on surfaces | Black, dark gray text |
| **Error** | Error states | Red (#D32F2F or similar) |
| **Warning** | Cautionary states | Amber/orange |
| **Success** | Positive confirmation | Green |
| **Info** | Informational | Blue |

### Color Usage Rules

1. **60-30-10 Rule**: 60% dominant (surface), 30% secondary, 10% accent
2. **Never use color alone** to convey meaning (accessibility: colorblind users)
3. **Semantic consistency**: Same color = same meaning throughout the app
4. **Contrast requirements**:
   - Text on background: 4.5:1 (AA) or 7:1 (AAA)
   - Large text: 3:1 minimum
   - Interactive elements: 3:1 against adjacent colors
5. **Dark mode**: Don't just invert colors — use elevated surfaces and reduced saturation
6. **Limited palette**: 3-5 colors maximum (plus neutrals)

### Color Psychology (Use Cautiously)

| Color | Association | UI Use |
|-------|-------------|--------|
| Blue | Trust, calm, professionalism | Primary UI color (most popular for good reason) |
| Red | Urgency, error, danger | Destructive actions, errors, alerts |
| Green | Success, nature, go | Confirmation, positive states |
| Orange/Amber | Warning, energy | Caution, attention-needed states |
| Purple | Premium, creativity | Premium features, creative tools |
| Gray | Neutral, disabled | Disabled states, secondary content |

### Dark Mode Design

- **Surface elevation**: Lighter backgrounds for elevated elements
- **Reduced saturation**: Highly saturated colors on dark backgrounds cause eye strain
- **White text**: Use 87% opacity for primary, 60% for secondary, 38% for disabled
- **Shadows**: Less visible on dark; use subtle borders or elevation through lightness
- **Test thoroughly**: Colors that work in light mode may not in dark mode

## Layout and Spacing

### Spacing System
Use a consistent spacing scale (multiples of a base unit):

```
Base: 4px (or 8px)

4px   — Tight spacing (within related items)
8px   — Default element spacing
12px  — Between related groups
16px  — Section padding
24px  — Between sections
32px  — Major section breaks
48px  — Page-level spacing
64px  — Hero/feature spacing
```

### Grid Systems

**Mobile (Single Column)**:
- Content width: 100% minus horizontal margins
- Horizontal margins: 16-20px
- Content flows vertically

**Tablet (Multi-Column)**:
- 8 or 12 column grid
- Gutters: 16-24px
- Margins: 24-32px

**Desktop (Multi-Column)**:
- 12 column grid
- Max content width: 1200-1440px
- Gutters: 24-32px
- Margins: auto (centered)

### Alignment Principles

- **Align everything** to a grid or axis — misalignment creates visual tension
- **Left-align text** for readability (LTR languages)
- **Center-align** only for short text (titles, CTAs, empty states)
- **Right-align** numbers in tables for easy comparison
- **Area alignment**: Align by visual weight, not geometric center (e.g., play button triangles)
- **Edge alignment**: Align elements by their edges, creating strong visual connections

### Whitespace

**Horror Vacui** vs. strategic whitespace:
- Novice designers fill every pixel. Expert designers use space to create clarity.
- Whitespace is not "empty" — it's active. It groups, separates, and emphasizes.
- **Micro whitespace**: Padding within elements (buttons, cards)
- **Macro whitespace**: Margins between sections, page edges
- **Active whitespace**: Intentionally placed to direct attention
- **Passive whitespace**: Natural whitespace from element layout

Rules:
- More whitespace = more perceived quality/luxury
- Less whitespace = more perceived value/density (but at cost of clarity)
- Never less than 8px between interactive elements
- Content breathing room: at least 16px padding inside containers

## Iconography

### Icon Design Rules

1. **Recognizable at small sizes**: Test at 16px, 24px, 32px
2. **Consistent style**: All icons in an app should share the same style (outline, filled, rounded)
3. **Paired with labels**: Icons alone are ambiguous. Always provide text labels for navigation icons.
4. **Standard metaphors**: Use established meanings (gear=settings, magnifier=search, house=home)
5. **Minimum details**: Remove every element that doesn't aid recognition
6. **Consistent optical weight**: All icons should feel the same visual weight at the same size

### Icon + Label Combinations

| Position | Use When |
|----------|----------|
| Icon left of text | Standard for buttons, list items |
| Icon above text | Tab bars, grid menus |
| Icon only | Only for universally understood icons (close, search, menu) with tooltip |
| Text only | When the action needs no icon (form labels, text links) |

### Iconic Representation (Lidwell)

| Type | Description | Example |
|------|-------------|---------|
| **Similar** | Resembles the referent | Camera icon for camera |
| **Example** | Instance of a category | Fork/knife for restaurants |
| **Symbolic** | Convention-based | Heart for favorites |
| **Arbitrary** | Learned association | Floppy disk for save |

- Similar and example icons are most intuitive
- Symbolic icons require initial learning but are efficient once learned
- Arbitrary icons should always have labels

## Golden Ratio and Proportions

### Golden Ratio (1:1.618)
- Pleasing proportions for rectangles, layout divisions
- Content area: sidebar ratio ≈ 1.618:1
- Not mandatory — but useful as a starting point for proportional layouts

### Fibonacci Sequence in Design
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89...

- Useful for spacing scales: 8, 13, 21, 34, 55px
- Image cropping: Fibonacci spiral for focal points
- Component sizing: related elements in Fibonacci ratios

### Rule of Thirds
- Divide canvas into 3x3 grid
- Place focal elements at intersection points
- Especially useful for hero images, onboarding illustrations
- Creates more dynamic compositions than centering

## Depth and Elevation

### Elevation System

| Level | Shadow | Use |
|-------|--------|-----|
| 0 | None | Background surface |
| 1 | Subtle (1-2px) | Cards, raised surfaces |
| 2 | Medium (4-6px) | Floating elements, dropdowns |
| 3 | Strong (8-12px) | Modals, dialogs |
| 4 | Dramatic (16-24px) | Overlays, menus |

### Shadow Rules
- Shadow direction: consistent light source (typically top-left)
- Larger shadow = more elevation = more importance
- Use sparingly — too many shadow levels create confusion
- Dark mode: reduce shadow opacity or use surface lightness instead
- Offset > blur for crisper, more modern shadows

## Contour Bias

Curved vs. angular shapes evoke different responses:

| Shape | Perception | Use For |
|-------|-----------|---------|
| Rounded corners | Friendly, approachable, safe | Consumer apps, onboarding, success states |
| Sharp corners | Professional, precise, efficient | Enterprise tools, data-heavy interfaces |
| Circles | Complete, unified, personal | Avatars, status indicators |
| Organic shapes | Natural, creative, playful | Creative tools, children's apps |

- Default to rounded corners (4-16px radius) for most UI elements
- Consistency: choose a corner radius and use it everywhere
- Cards, buttons, inputs should share the same corner radius

## References

- Lidwell et al. (2010). *Universal Principles of Design*: Alignment, Area Alignment, Closure, Color, Contour Bias, Figure-Ground Relationship, Fibonacci Sequence, Golden Ratio, Good Continuation, Gutenberg Diagram, Hierarchy, Highlighting, Horror Vacui, Iconic Representation, Layering, Legibility, Orientation Sensitivity, Proximity, Similarity, Von Restorff Effect
- Norman, D. (2013). *The Design of Everyday Things*, Chapter 1 (Signifiers, Affordances)
