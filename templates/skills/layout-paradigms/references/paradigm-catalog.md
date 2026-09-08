# Paradigm catalog and blueprint reference

This catalog details the structural rules, responsive considerations, and
anti-patterns for each layout paradigm supported by Design Orchestra.

## 1. Asymmetrical split and interactive viewport

### Composition blueprint
- **Desktop Grid:** 12-column grid. Columns 1–5 (or 1–6) house product title,
  value proposition, secondary social proof snippet, and primary CTA. Columns
  6–12 (or 7–12) contain a bounded interactive viewport, canvas, or interactive
  state simulator.
- **Hero Stance:** Left-heavy reading entry with immediate interactive
  engagement on the right.
- **Mobile Reflow:** Single column. Headline and CTA anchor the top; the
  interactive viewport reflows below the primary CTA as an expandable or
  scrollable interactive sandbox with clear touch affordances.

### Anti-patterns to avoid
- Stacking an oversized inert screenshot that provides no interactivity.
- Centering the headline text above an asymmetrical split (creates visual
  dissonance).

## 2. Editorial masthead and marginalia

### Composition blueprint
- **Desktop Grid:** Asymmetrical multi-column editorial grid. A prominent,
  elegant top masthead sets issue or edition numbers, category tags, and
  date or status. The primary narrative unfolds in a main reading column
  (columns 3–9), flanked by marginalia (columns 10–12) carrying footnotes,
  author credentials, and contextual citations.
- **Hero Stance:** Authoritative, high-density editorial framing. Heavy reliance
  on serif/grotesque typographic contrast and deliberate vertical rhythm.
- **Mobile Reflow:** Marginalia collapses into inline accordion footnotes or
  distinct pull-quote dividers following each section.

### Anti-patterns to avoid
- Burying the conversion CTA so deeply in text that visitors cannot take action.
- Relying on decorative drop-caps that fail WCAG screen-reader pronunciation
  tests.

## 3. Dynamic bento system (hierarchical tiles)

### Composition blueprint
- **Desktop Grid:** 4-column, multi-row CSS grid with irregular spanning
  (`grid-column: span 2`, `grid-row: span 2`).
  - **Anchor Tile (Hero):** 2x2 area demonstrating the primary value or
    interactive workflow.
  - **Metric Tile:** 1x1 area showing a real, verified statistic with context.
  - **Workflow Tile:** 2x1 horizontal tile detailing integration or process.
  - **Detail Tile:** 1x1 or 1x2 vertical tile illustrating privacy, security, or
    speed.
- **Hero Stance:** Organized complexity with clear hierarchy. The anchor tile
  immediately attracts primary focus.
- **Mobile Reflow:** Reflows into a single-column card stack sorted strictly by
  priority (Anchor Tile first, followed by Workflow, then Metrics).

### Anti-patterns to avoid
- "Card soup": Giving all tiles equal dimensions, equal visual weight, and equal
  content types (which degenerates into the generic 3-card grid).
- Cluttering tiles with decorative gradients rather than actionable data.

## 4. Monumental typographic rhythm

### Composition blueprint
- **Desktop Grid:** Generous margins (80px+ horizontal padding). Minimal
  chrome. A commanding display headline (72px–120px) commanding 60% of
  above-the-fold viewport height, supported by a crisp 18px body paragraph and a
  solitary primary action.
- **Hero Stance:** Extreme clarity, restrained authority, and confidence.
  Relies on negative space and typographic personality rather than cards or
  illustrations.
- **Mobile Reflow:** Display font scales fluidly using `clamp(2.5rem, 8vw, 6rem)`
  to preserve hierarchy and prevent awkward multi-line hyphenation.

### Anti-patterns to avoid
- Using generic Inter or system fonts without letterspacing, weight contrast, or
  typographic voice.
- Neglecting WCAG contrast ratios on subtle secondary captions.

## 5. Live terminal and sandbox playground

### Composition blueprint
- **Desktop Grid:** Split or stacked layout with an authentic, interactive shell
  window or code editor front-and-center. Includes copyable install commands,
  tabbed language selectors, and real-time execution output.
- **Hero Stance:** Developer-first utility. Proves the tool works within 3
  seconds of page load.
- **Mobile Reflow:** The terminal maintains fixed horizontal scroll for code
  snippets with an explicit "Copy" button to avoid mobile typing frustrations.

### Anti-patterns to avoid
- Fake animated terminal typing that prevents user text selection or takes 15
  seconds to finish typing.
- Low-contrast green-on-black terminal themes that fail accessibility audits.

## 6. Chaptered narrative stream

### Composition blueprint
- **Desktop Grid:** Pinned side rail or sticky progress indicator on the left
  (columns 1–3) highlighting progress through narrative chapters:
  - `01 / Problem` (Current industry friction)
  - `02 / Architecture` (How the solution functions)
  - `03 / Verification` (Evidence, benchmarks, customer case studies)
  - `04 / Onboarding` (Clear next step)
- **Hero Stance:** Structured, sequential storytelling that builds conviction
  before presenting the CTA.
- **Mobile Reflow:** Sticky side rail transforms into a compact horizontal
  stepper bar pinned under the top navigation.

### Anti-patterns to avoid
- Scroll-jacking or forcing arbitrary scroll velocities.
- Missing an early exit/CTA for visitors who are already ready to convert.

## 7. Utility-centric compact bar and control deck

### Composition blueprint
- **Desktop Grid:** Ultra-efficient 64px–80px persistent control deck with
  search inputs, filter toggles, live status gauges, and direct action triggers.
  The content area below immediately presents data, results, or tool output.
- **Hero Stance:** Zero marketing fluff. The user is in the application within 1
  second.
- **Mobile Reflow:** Control deck collapses into an accessible bottom sheet or
  sticky action drawer with clear touch targets (minimum 44x44px).

### Anti-patterns to avoid
- Hiding primary utilities behind multi-level hamburger dropdowns.
- Sacrificing responsive ergonomics for visual density.

## 8. Bifurcated comparative canvas

### Composition blueprint
- **Desktop Grid:** Vertical split canvas dividing the screen into two distinct
  contrasting zones:
  - Left Zone: "Before / Without" (friction, manual toil, fragmentation).
  - Right Zone: "After / With" (clarity, automation, unified workflow).
  - Or Persona Split: "For Developers" vs. "For Designers".
- **Hero Stance:** Dynamic dual perspective that clarifies product
  differentiation immediately.
- **Mobile Reflow:** Interactive tab toggle or swipeable split card allowing
  users to compare states without visual squishing.

### Anti-patterns to avoid
- Caricaturing the "Before" state with hostile or unreadable design.
- Creating competing primary actions that confuse user routing.
