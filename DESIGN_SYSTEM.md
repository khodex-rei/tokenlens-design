# AI Guardrail Design System

> Version: 1.0.0
> Last updated: 2026-05-03
> Applies to: all client-side (SvelteKit) implementation work

---

## 1. Design Philosophy

**"Warm Precision"** — enterprise credibility without enterprise coldness.

Our visual identity sits at the intersection of three influences:

- **Stripe** — warm editorial tones, human copy, generous whitespace
- **Linear** — surgical precision, subtle depth, purposeful motion
- **Dreamcore** — soft iridescence, pastel holographic gradients, jelly translucency

The result: interfaces that feel trustworthy yet playful, technical yet approachable.

---

## 2. Color System

### 2.1 Primary Palette

| Token | Hex | Usage |
|---|---|---|
| `--brand` | `#863bff` | Legacy purple — sparingly, for brand moments only |
| `--pink` | `#ffb8d0` | Primary accent, CTAs, highlights |
| `--blue` | `#a8d8ff` | Secondary accent, info states, links |
| `--lavender` | `#c4b5ff` | Tertiary accent, gradients, hover states |
| `--cyan` | `#a0f0e8` | Quaternary accent, success, pulse indicators |
| `--peach` | `#ffd4b8` | Warm complement, tags, badges |
| `--yellow` | `#fff4a8` | Rare accent, stars, special callouts |

### 2.2 Neutral Palette

| Token | Hex | Usage |
|---|---|---|
| `--ink` | `#1a1a3e` | Primary text, headlines |
| `--ink-secondary` | `#4a4a6e` | Body text, descriptions |
| `--ink-muted` | `#7a7a9e` | Labels, captions, disabled |
| `--ink-light` | `#a0a0c0` | Placeholders, dividers |

### 2.3 Surface Palette

| Token | Hex | Usage |
|---|---|---|
| `--glass-bg` | `rgba(255,255,255,0.25)` | Card backgrounds, nav |
| `--glass-border` | `rgba(255,255,255,0.4)` | Card borders, dividers |
| `--glass-highlight` | `rgba(255,255,255,0.6)` | Top inset shine |
| `--surface-warm` | `#faf8f5` | Fallback page background (legacy) |

### 2.4 Gradient Patterns

```css
/* Primary gradient — CTAs, badges, active states */
background: linear-gradient(135deg, var(--pink) 0%, var(--lavender) 50%, var(--blue) 100%);

/* Aurora background — page-level ambience */
background: linear-gradient(135deg, #f0f4ff 0%, #fff0f5 25%, #f5f0ff 50%, #e8f8f5 75%, #fff8f0 100%);

/* Text gradient — headlines, metrics */
background: linear-gradient(135deg, var(--cobalt), var(--lavender));
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```

---

## 3. Typography

### 3.1 Font Stack

| Role | Font | Weights | Fallback |
|---|---|---|---|
| Display / headlines | Space Grotesk | 400, 500, 600, 700 | sans-serif |
| UI / body | Inter | 300, 400, 500, 600, 700 | system-ui, sans-serif |
| Editorial (legacy) | Newsreader | 400 italic | Georgia, serif |

### 3.2 Scale

| Token | Size | Line-height | Weight | Usage |
|---|---|---|---|---|
| `hero-title` | `clamp(40px, 7vw, 72px)` | 1.05 | 700 | Hero headlines |
| `section-title` | `clamp(28px, 4vw, 44px)` | 1.15 | 700 | Section headers |
| `card-title` | `20px` | 1.3 | 600 | Card headlines |
| `body` | `15px` | 1.6 | 400 | Paragraphs |
| `body-sm` | `14px` | 1.6 | 400 | Card descriptions |
| `label` | `13px` | 1.4 | 600 | Badges, eyebrows |
| `caption` | `12px` | 1.4 | 500 | Tags, metadata |

### 3.3 Rules

- Headlines: `-0.03em` letter-spacing (tight)
- Body: default letter-spacing
- Labels: `0.1em` letter-spacing, uppercase
- Never use font-weight below 400 for readability

---

## 4. Spacing System

| Token | Value | Usage |
|---|---|---|
| `--s-1` | `4px` | Icon gaps, tight padding |
| `--s-2` | `8px` | Inline spacing |
| `--s-3` | `12px` | Component internal |
| `--s-4` | `16px` | Standard padding |
| `--s-5` | `20px` | Card padding |
| `--s-6` | `24px` | Section gutters |
| `--s-8` | `32px` | Component gaps |
| `--s-10` | `40px` | Card internal padding |
| `--s-12` | `48px` | Section margins |
| `--s-16` | `64px` | Large sections |
| `--s-20` | `80px` | Hero padding |
| `--s-24` | `96px` | Major section breaks |
| `--s-32` | `128px` | Hero top padding |

---

## 5. Shape & Radius

| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | `20px` | Small cards, tags |
| `--radius-md` | `28px` | Medium cards, inputs |
| `--radius-lg` | `40px` | Large cards, modals |
| `--radius-full` | `9999px` | Buttons, badges, pills |

### 5.1 Blob Morphing

For organic shapes (logo, decorative elements):

```css
border-radius: 50% 40% 60% 50% / 60% 50% 40% 60%;
animation: blob-morph 8s ease-in-out infinite;

@keyframes blob-morph {
  0%, 100% { border-radius: 50% 40% 60% 50% / 60% 50% 40% 60%; }
  33% { border-radius: 40% 60% 50% 60% / 50% 60% 50% 40%; }
  66% { border-radius: 60% 50% 40% 50% / 40% 50% 60% 50%; }
}
```

---

## 6. Elevation & Depth

### 6.1 Glassmorphism

All elevated surfaces use the glass pattern:

```css
.glass {
  background: rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(20px) saturate(1.3);
  -webkit-backdrop-filter: blur(20px) saturate(1.3);
  border: 1px solid rgba(255, 255, 255, 0.4);
  box-shadow: 
    0 8px 32px rgba(168, 216, 255, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.6);
}
```

### 6.2 Jelly Button

```css
.jelly-btn {
  background: linear-gradient(135deg, var(--pink) 0%, var(--lavender) 50%, var(--blue) 100%);
  border-radius: 9999px;
  box-shadow: 
    0 4px 20px rgba(196, 181, 255, 0.4),
    0 2px 8px rgba(255, 184, 208, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.5);
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.jelly-btn:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 
    0 12px 40px rgba(196, 181, 255, 0.5),
    0 4px 16px rgba(255, 184, 208, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.6);
}
```

### 6.3 Card Hover

```css
.jelly-card {
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.jelly-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 
    0 20px 60px rgba(196, 181, 255, 0.25),
    0 8px 24px rgba(168, 216, 255, 0.15);
  border-color: rgba(255, 255, 255, 0.6);
}
```

---

## 7. Motion & Animation

### 7.1 Easing

| Name | Value | Usage |
|---|---|---|
| `ease-spring` | `cubic-bezier(0.34, 1.56, 0.64, 1)` | Hover, pop-in |
| `ease-smooth` | `cubic-bezier(0.4, 0, 0.2, 1)` | Transitions |
| `ease-float` | `ease-in-out` | Ambient motion |

### 7.2 Durations

| Context | Duration |
|---|---|
| Hover transitions | `0.3s` |
| Card hover | `0.4s` |
| Page transitions | `0.5s` |
| Ambient float | `20s` (loop) |
| Blob morph | `8s` (loop) |
| Blob bounce | `3s` (loop) |
| Pulse glow | `2s` (loop) |

### 7.3 Performance Rules

- Use `transform` and `opacity` only for animations
- Avoid animating `width`, `height`, `top`, `left`
- Add `will-change: transform` on animated elements
- Respect `prefers-reduced-motion` — disable ambient animations

---

## 8. Iconography

### 8.1 Style

- Inline SVG only — no icon libraries
- 24×24px default, 18×18px for compact contexts
- 2px stroke width, round caps and joins
- Stroke color matches context (brand gradient for CTAs, ink-muted for secondary)

### 8.2 Common Icons

Keep a set of standard inline SVGs for:
- Check / cross (feature lists)
- Arrow right (CTAs)
- Shield (security)
- Chart (analytics)
- Users (teams)
- Zap (speed)
- Lock (privacy)
- Bell (alerts)

---

## 9. Layout Patterns

### 9.1 Page Structure

```
[Nav — glass pill, fixed top]
[Hero — 100vh, centered, aurora bg]
[Section — max-width 1200px, centered]
  [Section header — eyebrow + title + subtitle]
  [Content grid — 3-col or 2-col]
[Metrics bar — 4-col glass cards]
[CTA — centered, blob decorations]
[Footer — glass strip]
```

### 9.2 Grid

- Default: 3-column for cards, 2-column for features
- Gap: `20px` (`--s-5`)
- Max-width: `1200px`
- Mobile: single column, `768px` breakpoint

### 9.3 Responsive Breakpoints

| Breakpoint | Behavior |
|---|---|
| `> 768px` | Full layout, 3-col grids |
| `<= 768px` | Single column, reduced padding, hidden nav links |

---

## 10. Component Patterns

### 10.1 Navigation

- Glass pill shape, fixed top
- Logo: blob-morphing gradient circle + "AI Guardrail" in Space Grotesk
- Links: subtle underline gradient on hover
- CTA: jelly button (secondary variant)

### 10.2 Hero

- 100vh, flex centered
- Aurora orbs behind (fixed, pointer-events: none)
- 3 bouncing blob decorations (pink, blue, lavender)
- Badge: glass pill with pulse dot
- Title: gradient text on key phrase
- Subtitle: Inter, muted ink
- CTA: jelly primary + glass secondary

### 10.3 Cards

- Glass background, blur backdrop
- Top gradient border (rainbow stripe)
- Inset highlight gradient
- Icon: gradient circle with SVG
- Hover: lift + scale + enhanced shadow

### 10.4 Buttons

**Primary (jelly):**
- Rainbow gradient background
- Cobalt text
- Pill shape
- Spring hover animation

**Secondary (glass):**
- Transparent background
- Glass border
- Ink-secondary text
- Lift on hover

**Ghost:**
- No background
- Ink-muted text
- Subtle hover color change

### 10.5 Badges

- Glass pill shape
- Uppercase, 12px, 600 weight
- Cobalt text
- Eyebrow labels: "Use cases", "Features", "Workflow"

### 10.6 Metrics

- Glass card container
- Gradient text for value (Space Grotesk, 40px)
- Muted label below
- Top gradient accent line

---

## 11. Background System

### 11.1 Aurora Layer

Fixed full-screen layer with 3–4 gradient orbs:

```css
.aurora-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  opacity: 0.4;
  animation: float 20s ease-in-out infinite;
}
```

Colors: pink (top-left), blue (top-right), lavender (bottom-left), cyan (bottom-right).

### 11.2 Page Background

```css
background: linear-gradient(135deg, #f0f4ff 0%, #fff0f5 25%, #f5f0ff 50%, #e8f8f5 75%, #fff8f0 100%);
background-attachment: fixed;
```

---

## 12. Content Tone

- Headlines: bold, direct, benefit-driven
- Body: conversational, no jargon
- CTAs: action-oriented, low friction ("Get started free", "See use cases")
- Badges: factual, not hype ("Now with multi-tenant workspaces")
- No emojis — use inline SVG icons

---

## 13. Implementation Rules

### 13.1 CSS Architecture

- Use CSS custom properties (variables) for all tokens
- No hardcoded values in component CSS
- Prefer `rem`/`px` over `em` for consistency
- Use `clamp()` for responsive typography

### 13.2 SvelteKit Specifics

- Scoped component styles where possible
- Global CSS for design tokens in `app.css`
- Inline SVG components for icons
- `scroll-behavior: smooth` on html

### 13.3 Accessibility

- Minimum contrast ratio: 4.5:1 for body text
- Focus states: visible outline, 2px offset
- `prefers-reduced-motion`: disable ambient animations
- Semantic HTML: nav, main, section, footer

### 13.4 Performance

- No external icon libraries (inline SVG only)
- Google Fonts: preconnect + display=swap
- Limit font weights to needed variants
- `will-change` on animated elements only

---

## 14. File Organization

```
design/
  index.html              # Entry point (landing)
  dreamcore-landing.html  # Full landing page
  dreamcore-pricing.html  # Pricing page
  landing-v1.html         # Legacy warm editorial
  landing-v2.html         # Legacy expanded landing
  pricing.html            # Legacy pricing
  DESIGN_SYSTEM.md        # This file
  .github/
    workflows/
      pages.yml           # GitHub Pages deployment
```

---

## 15. Version History

| Version | Date | Changes |
|---|---|---|
| 1.0.0 | 2026-05-03 | Initial dreamcore design system |

---

## 16. References

- **Live design repo:** https://github.com/khodex-rei/ai-guardrail-design
- **Deployed pages:** https://khodex-rei.github.io/ai-guardrail-design/
- **Dreamcore landing:** https://khodex-rei.github.io/ai-guardrail-design/dreamcore-landing.html
- **Dreamcore pricing:** https://khodex-rei.github.io/ai-guardrail-design/dreamcore-pricing.html
