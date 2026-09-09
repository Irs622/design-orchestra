# Anti-generic AI audit and slop prevention

Use this audit whenever a landing page needs to feel intentional, authored, and
specific to its product rather than assembled from familiar, unexamined AI
generation parts.

The problem is never that AI was used to draft copy, wireframes, or frontend
code. The failure is unexamined accumulation of generic tropes, excessive
decoration, abstract claims, and cookie-cutter layouts that lack design judgment,
real constraints, and visitor empathy.

## Signals to investigate

These signals matter most when several appear together without a clear product
or brand reason:

- **Excessive gradients:** ubiquitous purple-to-blue or neon mesh gradients
  applied indiscriminately across background, headings, buttons, cards, borders,
  and icons.
- **Radial blur orbs and glows:** blurred floating blobs, ambient radial
  backlights, and neon backdrops used as a shortcut to create false visual depth.
- **Glassmorphism overuse:** stacking frosted glass panels and blurry borders
  across navbars, cards, modals, and buttons until visual contrast collapses.
- **Unconstrained palette inflation:** using six or more vibrant saturated hues
  without clear semantic roles (canvas, ink, surface, action, and feedback).
- **Universal extreme radius:** blindly applying large border radii to every
  card, button, input, navbar, modal, and container, destroying boundary clarity.
- **Homogeneous shadowing:** heavy multi-layer drop shadows on all cards,
  eliminating elevation hierarchy.
- **Template hero formula:** an oversized centred headline, short vague subhead,
  one pill CTA, and an unmotivated dashboard mockup.
- **The automatic 3-card row:** exactly three rounded feature cards with uniform
  height and width, each containing an icon, title, and one sentence.
- **Section bloat:** generating every conceivable section (logo cloud, feature
  grid, stats, testimonials, pricing, FAQ) even when the user task calls for a
  concise narrative.
- **Standard header uniformity:** repeating the default logo-left, three links
  centre, CTA-right pattern regardless of information architecture.
- **Decorative badges and fake status:** unprompted green pulsing "Live" dots,
  "AI Powered 99%" chips, fake activity notifications, or showcase badges.
- **Irrelevant dashboard mockups:** complex charts with arbitrary graphs and fake
  metrics inserted merely to fill white space rather than communicate a real
  feature.
- **Meaningless decorative noise:** drifting particles, isolated sparkles,
  floating cards, and abstract 3D spheres or donuts.
- **Icon saturation and handwritten SVGs:** attaching icons to every sentence,
  and handwriting inline SVG code instead of relying on a clean installed icon
  package.
- **Abstract buzzword inflation:** grandiose claims ("Empowering next-generation
  intelligent innovation") that fail the generic company test.
- **Absence of real proof:** invented quotes, placeholder logos, synthetic
  performance percentages, or vague testimonials lacking named provenance.
- **Purposeless motion:** drift animations, auto-scrolling logo marquees, and
  entrance parallax that add visual noise and ignore reduced-motion settings.

Do not treat any single item as forbidden. A verified status can be useful; a
glass surface can suit a selected system. The failure is unexamined accumulation
and repetition.

## Five evaluation stress tests

Before approving any landing page, subject the design to these five evaluation
tests:

1. **Remove effects test:** turn off all gradients, backdrops, box shadows,
   blur orbs, and entrance animations. The typography hierarchy, grid, content
   sequence, contrast, and layout structure must remain clear, readable, and
   intentional without decoration.
2. **Generic company test:** replace the product name in all headlines and copy
   with "Acme Corp" or "Generic SaaS Tool". If the copy still reads smoothly
   without sounding broken or awkward, it is too abstract and must be rewritten
   with concrete nouns, metrics, and workflows.
3. **De-branded screenshot test:** take a full-page screenshot and mask out the
   logo and product name. A designer or visitor must still recognize the
   product category and personality through its distinct layout, voice, and
   visual system.
4. **Black and white test:** convert the entire viewport to grayscale. Visual
   hierarchy, primary CTAs, content boundaries, and interactive states must
   remain immediately obvious through contrast, scale, and density alone.
5. **The 30% reduction test:** strip out 20% to 30% of purely decorative
   elements (floating tags, background meshes, redundant badge chips). If the
   page becomes significantly faster to comprehend, those elements were slop.

## Anti-slop design principles

- **Start from the user task, not the screenshot:** design for comprehension,
  orientation, accessibility, and conversion rather than a social media post.
- **Establish strict design constraints:** two primary brand colors, one
  semantic accent, maximum two font families, three defined border-radius steps,
  and a unified installed icon family.
- **Earned decoration:** every surface treatment, gradient, icon, or motion
  keyframe must earn its place by aiding wayfinding, user feedback, or brand
  expression.
- **Concrete over abstract:** replace vague marketing promises with tangible
  verbs, actual data objects, and verifiable outcomes.

## Pre-deployment checklist

### Visual and layout
- [ ] Gradients are restrained, purposeful, and never the primary color system.
- [ ] Border radius follows a clear hierarchical system rather than blanket
      rounding.
- [ ] Surfaces and shadows establish true elevation layers, not decorative
      muddiness.
- [ ] No fake green live dots, decorative status pills, or unprompted AI score
      badges.
- [ ] Layout structure breaks predictable formulas using deliberate layout
      paradigms (from the layout-paradigms skill).

### Content and copy
- [ ] Primary headline clearly states what the product is and for whom.
- [ ] Zero abstract buzzwords used without concrete context.
- [ ] Proof elements (metrics, quotes, logos) are 100% verified and authentic.
- [ ] Sections serve a necessary communication step; unnecessary padding
      sections are removed.

### Interaction and UX
- [ ] Clear primary CTA with visible keyboard focus and distinct hover states.
- [ ] Navigation matches the product's information architecture.
- [ ] Motion is tied to user interaction, orientation, or feedback; strictly
      respects `prefers-reduced-motion`.
- [ ] Responsive design genuinely re-thinks flow and touch targets on mobile,
      not merely scaling desktop text.
