# Cognitive Principles for Design

Psychology-grounded principles that govern how users perceive, think, learn, and act within interfaces. Drawn from Norman's psychology of everyday actions and Lidwell/Holden/Butler's cognitive design principles.

## The Psychology of Everyday Actions

### Norman's Seven Stages of Action

Every user interaction follows this cycle. Design failures happen when any stage breaks down.

```
1. Goal       → What do I want to accomplish?
2. Plan       → What are the alternative action sequences?
3. Specify    → What action can I do now?
4. Perform    → How do I do it?
5. Perceive   → What happened?
6. Interpret  → What does it mean?
7. Compare    → Is this what I wanted?
```

**Gulf of Execution** (stages 2-4): The gap between what users intend and what the interface allows.
- Bridged by: good affordances, signifiers, mapping, constraints
- Symptom: user knows what they want but can't figure out how

**Gulf of Evaluation** (stages 5-7): The gap between system state and user understanding.
- Bridged by: good feedback, conceptual models, system visibility
- Symptom: user did something but can't tell what happened

### Design Implications
- If users struggle to **start** an action → improve discoverability and signifiers
- If users perform the **wrong** action → improve constraints and mapping
- If users can't tell **what happened** → improve feedback
- If users **misinterpret** results → improve the conceptual model

## Attention and Perception

### Inattentional Blindness
Users miss unexpected elements, even prominent ones, when focused on a task.
- **Design rule**: Never rely solely on color, size, or position changes to communicate critical information
- **Fix**: Use motion, modals, or inline alerts to break through focused attention
- **Mobile**: Banner notifications are often missed; use persistent badges for important state

### Change Blindness
Users fail to detect changes between visual scenes, especially during interruptions.
- **Design rule**: Animate transitions so users perceive what changed
- **Fix**: Highlight differences; use toast/snackbar messages after state changes
- **Don't**: Silently update content without visual indication

### Selective Attention
Users attend to ~4 items simultaneously. Everything else is background.
- **Design rule**: Reduce competing visual elements. One primary action per screen.
- **Fix**: Visual hierarchy (size, contrast, color) directs attention to what matters
- **Mobile**: Single-column layouts naturally limit competing elements

### Orientation Sensitivity
People are especially sensitive to things that look like faces or figures.
- Anthropomorphic UI elements attract attention but can distract
- Profile images and avatars draw the eye before text content
- Use strategically for onboarding, empty states, error pages

## Memory and Cognitive Load

### Working Memory Limits
Modern research shows 4±1 chunks (not Miller's 7±2) for complex items.

| Type | Capacity | Design Application |
|------|----------|-------------------|
| Visual working memory | ~3-4 items | Limit visible options in dropdowns/menus |
| Verbal working memory | ~4-7 items | Keep navigation categories concise |
| Spatial working memory | ~3-4 locations | Minimize distinct layout regions |

### Chunking
Group related information into meaningful units to extend effective memory.
- **Phone numbers**: 4155551234 → (415) 555-1234
- **Navigation**: Group menu items by category with visual separators
- **Forms**: Section long forms into logical groups (Personal, Address, Payment)
- **Content**: Use headers, bullets, whitespace to chunk text

### Depth of Processing
Information processed more deeply is remembered better.

| Level | Example | Retention |
|-------|---------|-----------|
| Structural | "Is the text bold?" | Low |
| Phonetic | "Does it rhyme with X?" | Medium |
| Semantic | "Does it relate to your goal?" | High |

- **Design rule**: Connect information to user's goals and context for better retention
- **Onboarding**: Interactive tutorials (deep processing) > passive walkthroughs
- **Labels**: Meaningful labels > cryptic abbreviations

### Recognition Over Recall
It's easier to recognize something seen before than to recall it from memory.
- Show recent searches, browsing history, suggestions
- Use visual thumbnails instead of text-only lists
- Provide autocomplete for text inputs
- Display command menus (Cmd+K palettes) rather than expecting memorized shortcuts

### Serial Position Effect
Users remember the **first** (primacy) and **last** (recency) items in a sequence best.
- Place the most important navigation item first and last
- In onboarding flows, make the first and last screens most impactful
- In lists, critical information goes at the top or bottom, not buried in the middle

## Decision Making

### Hick's Law (Choice Overload)
**Decision time = a + b × log2(n)** where n = number of equally probable choices.

- 2 choices: ~0.3s decision → Good: toggle, binary choice
- 4 choices: ~0.6s decision → Good: segmented control
- 8+ choices: >1s decision → Consider: progressive disclosure, search, smart defaults
- 20+ choices: significant delay → Required: search, filters, categorization

**Strategies to reduce choice overload**:
1. Smart defaults (pre-select the most common option)
2. Progressive disclosure (show basics first, details on demand)
3. Categorization (group into meaningful categories)
4. Recommendation (highlight "Most Popular" or "Recommended")
5. Search (for large option sets)

### Paradox of Choice
More options = more anxiety, less satisfaction, more regret.
- Fewer well-curated options outperform unlimited choice
- "Editor's picks" and curated lists reduce decision anxiety
- Allow customization without requiring it

### Framing Effect
How information is presented dramatically affects decisions.
- "95% fat-free" > "5% fat" (positive framing)
- "Save $20" vs "20% off" — test which frame works for your context
- Error messages: frame as solutions, not problems ("Try again with..." not "Invalid input")
- Progress: "3 of 5 complete" > "2 remaining" (accomplishment framing)

### Anchoring
The first piece of information disproportionately influences subsequent judgments.
- Show the premium plan first to anchor price expectations
- Display original price alongside sale price
- First data point on a dashboard sets the mental baseline

### Cost-Benefit Analysis
Users intuitively weigh effort against reward for every interaction.
- High-cost, low-benefit = abandoned action (long forms for small features)
- Low-cost, high-benefit = eager engagement (one-tap sharing)
- Reduce cost: fewer steps, auto-fill, smart defaults, inline editing
- Increase perceived benefit: clear value propositions, immediate feedback

## Learning and Behavior

### Knowledge in the World vs. Knowledge in the Head

| In the World | In the Head |
|--------------|-------------|
| Labels, signs, instructions | Memory, training, experience |
| Slower but reliable | Faster but fallible |
| Design for first-time use | Design for expert efficiency |

**Best practice**: Support both. Labels for novices, shortcuts for experts.

### Two Types of Knowledge
1. **Knowledge OF** (declarative): Facts, rules — conveyed through labels, documentation
2. **Knowledge HOW** (procedural): Motor skills, habits — built through practice

- First-time users need declarative cues (labels, hints, tooltips)
- Repeat users develop procedural fluency (keyboard shortcuts, gestures)
- Support the transition: show shortcuts alongside button labels

### Classical Conditioning
Repeated pairing creates associations.
- Consistent sound/haptic for notifications → users learn to respond
- Consistent color for error states → red instantly signals problems
- Brand colors/sounds create emotional associations
- Be consistent — inconsistent signals break conditioning

### Operant Conditioning
Behaviors followed by rewards increase in frequency.

| Schedule | Pattern | Application |
|----------|---------|-------------|
| Continuous | Reward every time | Onboarding — acknowledge every completed step |
| Variable ratio | Random reward frequency | Engagement loops — social media feeds, pull-to-refresh |
| Fixed interval | Reward on schedule | Daily streaks, weekly summaries |
| Variable interval | Random timing | Push notifications with valuable content |

- Use continuous reinforcement for learning new behaviors
- Switch to variable schedules for sustained engagement
- Avoid manipulative patterns — align rewards with genuine user value

### Exposure Effect (Mere Exposure)
Repeated exposure increases preference, even without conscious recognition.
- Familiar UI patterns feel more trustworthy and usable
- Introduce new features gradually alongside familiar ones
- Radical redesigns feel worse initially — transition with care
- Jakob's Law: users prefer interfaces that work like ones they already know

## Error Psychology

### Two Types of Errors (Norman)

**Slips**: Unintended actions — the user knows the right thing but does the wrong thing.
- **Capture errors**: Habit overrides intent (typing old password after reset)
- **Description-similarity**: Wrong action on similar-looking target (delete vs. edit icon)
- **Mode errors**: Right action, wrong mode (typing in wrong field)
- **Memory-lapse**: Forgetting a step in a sequence

**Mistakes**: Wrong intention — the user's mental model is wrong.
- **Rule-based**: Applying wrong rule to situation
- **Knowledge-based**: Lack of knowledge leads to wrong plan
- **Memory-lapse**: Forgetting the goal mid-task

### Error Prevention Strategies

| Error Type | Prevention | Example |
|-----------|------------|---------|
| Slip: capture | Differentiate similar actions visually | Red "Delete" vs. blue "Edit" |
| Slip: mode | Show current mode prominently | Bold active tab, mode indicators |
| Mistake: rule | Provide clear guidance and constraints | Inline hints, format examples |
| Mistake: knowledge | Offer help in context | Tooltips, contextual help links |
| Both | Undo over confirmation | Gmail's "Undo Send" vs "Are you sure?" |

### The Forgiveness Principle
Design for error recovery, not just error prevention.
- Undo/redo for all destructive actions
- Drafts auto-saved regularly
- Trash/archive before permanent deletion
- "Did you mean...?" suggestions for search
- Easy escape from any state (clear back navigation)

## Emotional Design

### Norman's Three Levels of Processing

| Level | Focus | Design Response |
|-------|-------|----------------|
| **Visceral** | Immediate sensory reaction | Aesthetics, color, typography, animation |
| **Behavioral** | Usability and function | Efficiency, reliability, feedback |
| **Reflective** | Self-image and meaning | Brand, storytelling, personalization |

- All three levels matter — a beautiful but unusable design fails at behavioral
- An efficient but ugly design fails at visceral
- A functional but meaningless design fails at reflective

### Flow State
Users enter flow when challenge matches skill level.
- Too easy → boredom → add complexity or shortcuts
- Too hard → anxiety → add guidance or simplify
- Progressive difficulty: start simple, increase complexity as skill grows
- Remove interruptions during focused tasks (no popups during checkout)

### Aesthetic-Usability Effect
Users perceive attractive interfaces as more usable, and are more forgiving of minor usability issues.
- Invest in visual design — it's not superficial, it directly affects perceived usability
- First impressions are visceral: 50ms to form aesthetic judgment
- Beautiful error pages feel less frustrating
- But aesthetics cannot substitute for fundamental usability — it amplifies, not replaces

## References

- Norman, D. (2013). *The Design of Everyday Things*, Chapters 1-3, 5
- Lidwell et al. (2010). *Universal Principles of Design*: Chunking, Classical Conditioning, Cognitive Dissonance, Depth of Processing, Exposure Effect, Framing, Hick's Law, Inattentional Blindness, Mental Model, Operant Conditioning, Serial Position Effect
