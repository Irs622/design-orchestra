# Animation and 3D web craft reference

This guide provides technical standards and patterns for implementing purposeful
animations, micro-interactions, and 3D scenes in React landing pages without
introducing AI slop, performance regressions, or accessibility barriers.

## 1. Principles of purposeful motion

Motion must serve a functional purpose. Never animate elements simply because a
library is available.

| Purpose | Valid Use Case | Anti-Pattern to Ban |
|---|---|---|
| **Feedback** | Button press active states, input confirmation, copy-to-clipboard badges. | Infinite ambient pulsing, bouncing CTAs that distract from reading. |
| **Orientation and hierarchy** | Modal choreography, drawer sliding along interaction axis, tab switching indicator. | Staggering 20 elements with arbitrary 50ms delays that slow down user tasks. |
| **Narrative pacing** | Scroll-linked step transitions in a chaptered case study or product breakdown. | Scroll-jacking, erratic parallax, or hijacking mouse velocity. |
| **Continuity** | Layout transitions between collapsed and expanded states (e.g. Framer Motion layoutId). | Uncontrolled drifting particle dust or wandering neon blobs. |

## 2. Performance engineering and GPU compositing

To maintain high responsiveness and achieve a 90+ Lighthouse Performance score:

1. **Animate only composited properties:**
   - Stick strictly to `transform` (`translate3d`, `scale`, `rotate`) and
     `opacity`.
   - Never animate `width`, `height`, `margin`, `padding`, `top`, `left`, or
     `box-shadow` directly, as they trigger expensive layout recalculations and
     repaints.
2. **Restrained will-change:**
   - Apply `will-change: transform` only to active interactive elements, and
     remove it once the transition ends to prevent GPU memory bloat.
3. **Hardware acceleration:**
   - Use `transform: translateZ(0)` or `backface-visibility: hidden` when
     necessary to promote layers cleanly to the compositor.

## 3. Strict WCAG compliance: prefers-reduced-motion

Under WCAG 2.1 Success Criterion 2.3.3 (Animation from Interactions), visitors
who experience vestibular disorders or motion sickness must have a mechanism to
disable non-essential motion.

### CSS pattern
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

### Framer Motion pattern
```tsx
import { motion, useReducedMotion } from "framer-motion";

export function HeroCard({ children }: { children: React.ReactNode }) {
  const shouldReduceMotion = useReducedMotion();

  return (
    <motion.div
      initial={shouldReduceMotion ? { opacity: 1 } : { opacity: 0, y: 16 }}
      animate={{ opacity: 1, y: 0 }}
      transition={{ duration: shouldReduceMotion ? 0 : 0.3, ease: "easeOut" }}
    >
      {children}
    </motion.div>
  );
}
```

### GSAP pattern
import gsap from "gsap";

const prefersReducedMotion = typeof window !== "undefined" && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
if (!prefersReducedMotion) {
  gsap.from(".feature-node", { y: 20, opacity: 0, stagger: 0.08, duration: 0.4 });
} else {
  gsap.set(".feature-node", { opacity: 1, y: 0 });
}
```

## 4. 3D web craft (React Three Fiber, Spline, Three.js)

3D is an exceptional storytelling medium when used to showcase the tangible
mechanics of a real product, spatial data, or physical hardware. It becomes AI
slop when it manifests as an arbitrary floating purple metallic sphere or
untextured donut.

### Architectural rules for 3D

1. **Lazy loading and dynamic code splitting:**
   - Never include 3D dependencies (`three`, `@react-three/fiber`,
     `@splinetool/runtime`) in the critical initial bundle.
   - Always load 3D scenes dynamically behind `React.lazy` or Next.js
     `dynamic(..., { ssr: false })` with a lightweight, high-fidelity CSS/SVG
     or static 2D preview placeholder.

```tsx
import dynamic from "next/dynamic";

const ProductSpatialViewer = dynamic(
  () => import("./ProductSpatialViewer").then((mod) => mod.ProductSpatialViewer),
  {
    ssr: false,
    loading: () => <div className="aspect-video bg-neutral-900 rounded-lg animate-pulse" />,
  }
);
```

2. **Memory and resource management:**
   - WebGL contexts are limited and easily crash mobile browsers.
   - Always dispose of geometries, materials, textures, and render targets
     inside `useEffect` cleanup return functions.
   - Clamp device pixel ratio: `dpr={[1, Math.min(window.devicePixelRatio, 2)]}`.
     Never render at 3x DPR on mobile.

3. **Camera bounds and control restraint:**
   - When using OrbitControls:
     - Always enable damping (`enableDamping = true`, `dampingFactor = 0.05`).
     - Disable zoom unless explicitly required (`enableZoom = false`) to prevent
       trapping page scroll.
     - Clamp polar angles (`minPolarAngle={Math.PI / 4}`, `maxPolarAngle={Math.PI / 2}`)
       to prevent visitors from flipping the camera upside down and losing
       orientation.

4. **Graceful degradation:**
   - Provide an automatic static fallback if WebGL is unavailable, crashes, or
     fails performance heuristics on low-tier mobile devices.
