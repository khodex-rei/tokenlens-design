# AI Guardrail Design System

> Version: 2.0.0 — Dreamcore Edition
> Last updated: 2026-05-03
> Applies to: all client-side (SvelteKit) implementation work

---

## 1. Design Philosophy

**"Soft Iridescent Dreamcore"**

Our visual identity is a **soft iridescent 3D dreamcore / pastel holographic style**. It looks like a mix of **AI-generated toy design, kawaii surrealism, vaporwave lighting, and translucent clay/plastic rendering**.

The main feeling is **cute, unreal, soft, and glowing**. UI elements look like they are made from **semi-transparent jelly, frosted glass, soft vinyl, or glowing silicone**. The forms are simple and rounded, but the colors make them feel magical and synthetic.

> **Pastel holographic UI with soft-focus glow, translucent jelly material, dreamy gradients, and surreal kawaii forms.**

This style connects to several aesthetics:

- **Dreamcore** — surreal, nostalgic, slightly unreal
- **Kawaii surrealism** — cute elements mixed with strange fantasy
- **Vaporwave / Y2K gradients** — pastel neon blue-pink-purple blending
- **Designer toy / art toy style** — collectible figurine feel
- **Holographic / iridescent 3D** — colors shift across surfaces like light through glass
- **Soft AI fantasy rendering** — generated, smooth, dreamlike

---

## 2. Color Palette

The palette is very important. The colors blend smoothly into each other like a **rainbow gradient**, but they are not sharp or saturated like cyberpunk. They are more **milky, blurred, and luminous**.

The color effect is close to: **holographic gradient + aurora glow + translucent plastic scattering**.

### 2.1 Primary Palette

| Token | Hex | Name | Usage |
|---|---|---|---|
| `--pink` | `#ffb8d0` | Pastel pink | Primary accent, CTAs, highlights, jelly buttons |
| `--blue` | `#a8d8ff` | Baby blue | Secondary accent, info states, links, aurora orbs |
| `--lavender` | `#c4b5ff` | Lavender / periwinkle | Tertiary accent, gradients, hover states, rim light |
| `--cyan` | `#a0f0e8` | Soft cyan | Quaternary accent, success, pulse indicators, glow |
| `--peach` | `#ffd4b8` | Warm peach | Warm complement, tags, badges, secondary blobs |
| `--yellow` | `#fff4a8` | Light yellow | Rare accent, stars, special callouts, highlights |
| `--cobalt` | `#2d3a8c` | Deep ultramarine | Text on light gradients, headings, strong contrast |

### 2.2 Neutral Palette

| Token | Hex | Usage |
|---|---|---|
| `--ink` | `#1a1a3e` | Primary text, headlines — deep but not pure black |
| `--ink-secondary` | `#4a4a6e` | Body text, descriptions |
| `--ink-muted` | `#7a7a9e` | Labels, captions, disabled, ghost elements |
| `--ink-light` | `#a0a0c0` | Placeholders, dividers, subtle borders |

### 2.3 Surface / Material Palette

| Token | Value | Material | Usage |
|---|---|---|---|
| `--glass-bg` | `rgba(255,255,255,0.25)` | Frosted glass | Card backgrounds, nav, modals |
| `--glass-border` | `rgba(255,255,255,0.4)` | Frosted edge | Card borders, dividers, input outlines |
| `--glass-highlight` | `rgba(255,255,255,0.6)` | Subsurface shine | Top inset highlight on glass surfaces |
| `--jelly-bg` | `rgba(255,184,208,0.2)` | Translucent jelly | Soft tinted containers, hover states |
| `--jelly-border` | `rgba(255,184,208,0.35)` | Jelly edge | Soft tinted borders |

### 2.4 Gradient Patterns

```css
/* Primary rainbow gradient — CTAs, badges, active states, blob fills */
background: linear-gradient(135deg, var(--pink) 0%, var(--lavender) 50%, var(--blue) 100%);

/* Aurora background — page-level ambience, dreamy atmosphere */
background: linear-gradient(135deg, #f0f4ff 0%, #fff0f5 25%, #f5f0ff 50%, #e8f8f5 75%, #fff8f0 100%);
background-attachment: fixed;

/* Text gradient — headlines, metrics, important numbers */
background: linear-gradient(135deg, var(--cobalt), var(--lavender));
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;

/* Rim light gradient — top borders on cards, accent lines */
background: linear-gradient(90deg, var(--pink), var(--lavender), var(--blue), var(--cyan));
```

---

## 3. Typography

### 3.1 Font Stack

| Role | Font | Weights | Fallback | Personality |
|---|---|---|---|---|
| Display / headlines | Space Grotesk | 400, 500, 600, 700 | sans-serif | Playful, geometric, slightly quirky |
| UI / body | Inter | 300, 400, 500, 600, 700 | system-ui, sans-serif | Clean, neutral, highly readable |

Space Grotesk gives headlines a **toy-like, friendly geometric quality**. Inter keeps body text **invisible and functional**.

### 3.2 Scale

| Token | Size | Line-height | Weight | Letter-spacing | Usage |
|---|---|---|---|---|---|
| `hero-title` | `clamp(40px, 7vw, 72px)` | 1.05 | 700 | -0.03em | Hero headlines — bold, tight, impactful |
| `section-title` | `clamp(28px, 4vw, 44px)` | 1.15 | 700 | -0.02em | Section headers |
| `card-title` | `20px` | 1.3 | 600 | default | Card headlines |
| `body` | `15px` | 1.6 | 400 | default | Paragraphs — generous line height for readability |
| `body-sm` | `14px` | 1.6 | 400 | default | Card descriptions, secondary text |
| `label` | `13px` | 1.4 | 600 | 0.1em | Badges, eyebrows, uppercase labels |
| `caption` | `12px` | 1.4 | 500 | default | Tags, metadata, fine print |

### 3.3 Rules

- Headlines: tight letter-spacing for impact
- Body: default letter-spacing, generous line-height
- Labels: wide letter-spacing, uppercase, small — like toy packaging
- Never use font-weight below 400
- Gradient text only on display type, never on body

---

## 4. Spacing System

| Token | Value | Usage |
|---|---|---|
| `--s-1` | `4px` | Icon gaps, tight padding |
| `--s-2` | `8px` | Inline spacing, icon-text gap |
| `--s-3` | `12px` | Component internal padding |
| `--s-4` | `16px` | Standard padding, mobile gutters |
| `--s-5` | `20px` | Card padding, grid gaps |
| `--s-6` | `24px` | Section gutters |
| `--s-8` | `32px` | Component gaps, medium spacing |
| `--s-10` | `40px` | Card internal padding, large gaps |
| `--s-12` | `48px` | Section margins |
| `--s-16` | `64px` | Large sections, hero bottom |
| `--s-20` | `80px` | Major section padding |
| `--s-24` | `96px` | Major section breaks |
| `--s-32` | `128px` | Hero top padding (accounts for fixed nav) |

---

## 5. Shape Language

The shape language is:

- **rounded** — no sharp corners anywhere
- **simplified** — minimal detail, clean silhouettes
- **inflated** — elements feel puffy, soft, 3D
- **soft** — everything has a gentle, approachable form
- **minimal** — no ornamentation, no noise
- **childlike** — friendly, non-threatening
- **non-threatening** — even serious elements feel gentle

### 5.1 Radius Scale

| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | `20px` | Small cards, tags, compact elements |
| `--radius-md` | `28px` | Medium cards, inputs, dropdowns |
| `--radius-lg` | `40px` | Large cards, modals, feature panels |
| `--radius-full` | `9999px` | Buttons, badges, pills, avatars — fully rounded |

### 5.2 Blob Morphing

For organic shapes — logo, decorative blobs, floating elements:

```css
border-radius: 50% 40% 60% 50% / 60% 50% 40% 60%;
animation: blob-morph 8s ease-in-out infinite;

@keyframes blob-morph {
  0%, 100% { border-radius: 50% 40% 60% 50% / 60% 50% 40% 60%; }
  33% { border-radius: 40% 60% 50% 60% / 50% 60% 50% 40%; }
  66% { border-radius: 60% 50% 40% 50% / 40% 50% 60% 50%; }
}
```

This creates a **living, breathing, jelly-like** form that constantly shifts.

---

## 6. Materials and Texture

Objects do not look matte, metallic, or realistic. They look like:

- **jelly** — wobbly, translucent, tinted
- **frosted glass** — blurred, light-scattering, semi-transparent
- **soft rubber** — matte but soft, squeezable feel
- **vinyl toy** — smooth, collectible, slightly glossy
- **semi-transparent resin** — depth, color trapped inside
- **glowing silicone** — light emanates from within
- **diffused plastic** — soft highlights, no sharp reflections

There is almost no surface detail. The texture is **extremely smooth**. Avoid hard edges, scratches, pores, fabric, or realistic material noise.

### 6.1 Glassmorphism (Frosted Glass)

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

The `inset` highlight creates **subsurface scattering** — light passing through the top edge.

### 6.2 Jelly Button

```css
.jelly-btn {
  background: linear-gradient(135deg, var(--pink) 0%, var(--lavender) 50%, var(--blue) 100%);
  border-radius: 9999px;
  color: var(--cobalt);
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

The button feels like a **squishy, glowing jelly** that bounces when touched.

### 6.3 Jelly Card

```css
.jelly-card {
  background: rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(20px) saturate(1.3);
  border: 1px solid rgba(255, 255, 255, 0.4);
  border-radius: 40px;
  position: relative;
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}

/* Rainbow rim light at top */
.jelly-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--pink), var(--lavender), var(--blue), var(--cyan));
  opacity: 0.6;
}

/* Subsurface highlight */
.jelly-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(255,255,255,0.2) 0%, transparent 50%);
  pointer-events: none;
  border-radius: inherit;
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

## 7. Lighting

Lighting is one of the strongest parts of this style.

It uses:

- **very soft global illumination** — no harsh shadows
- **blurred highlights** — soft, diffused, not sharp
- **subsurface scattering** — light passes through, glows from within
- **bloom** — soft glow around bright elements
- **overexposure** — highlights can blow out slightly, dreamily
- **backlight / rim light** — edges catch light, especially rainbow gradients
- **gentle color bleeding** — colors softly spill into adjacent areas

The light feels like it **passes through the object** instead of only bouncing off it. That is why elements feel like **glowing toys or translucent creatures**.

### 7.1 Aurora Background System

Fixed full-screen layer with floating gradient orbs:

```css
.aurora {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
  overflow: hidden;
}

.aurora-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  opacity: 0.4;
  animation: float 20s ease-in-out infinite;
}

.aurora-orb-1 {
  width: 600px; height: 600px;
  background: radial-gradient(circle, var(--pink) 0%, transparent 70%);
  top: -10%; left: -10%;
}

.aurora-orb-2 {
  width: 500px; height: 500px;
  background: radial-gradient(circle, var(--blue) 0%, transparent 70%);
  top: 20%; right: -15%;
  animation-delay: -7s;
}

.aurora-orb-3 {
  width: 450px; height: 450px;
  background: radial-gradient(circle, var(--lavender) 0%, transparent 70%);
  bottom: 10%; left: 20%;
  animation-delay: -14s;
}

.aurora-orb-4 {
  width: 350px; height: 350px;
  background: radial-gradient(circle, var(--cyan) 0%, transparent 70%);
  bottom: -5%; right: 30%;
  animation-delay: -5s;
}

@keyframes float {
  0%, 100% { transform: translate(0, 0) scale(1); }
  25% { transform: translate(30px, -30px) scale(1.05); }
  50% { transform: translate(-20px, 20px) scale(0.95); }
  75% { transform: translate(40px, 10px) scale(1.02); }
}
```

These orbs create a **dreamy, ever-shifting atmosphere** behind the UI.

### 7.2 Blob Highlights

Decorative blobs have internal highlights to simulate **subsurface scattering**:

```css
.hero-blob::after {
  content: '';
  position: absolute;
  top: 15%; left: 20%;
  width: 25%; height: 15%;
  background: rgba(255, 255, 255, 0.7);
  border-radius: 50%;
  filter: blur(2px);
}
```

This creates a **soft specular highlight** like light hitting a jelly surface.

---

## 8. Motion and Animation

### 8.1 Easing

| Name | Value | Usage | Feel |
|---|---|---|---|
| `ease-spring` | `cubic-bezier(0.34, 1.56, 0.64, 1)` | Hover, pop-in | Bouncy, elastic, jelly-like |
| `ease-smooth` | `cubic-bezier(0.4, 0, 0.2, 1)` | Transitions | Gentle, natural |
| `ease-float` | `ease-in-out` | Ambient motion | Drifting, dreamy |

### 8.2 Durations

| Context | Duration | Feel |
|---|---|---|
| Hover transitions | `0.3s` | Quick, responsive |
| Card hover | `0.4s` | Slightly slower, more dramatic |
| Page transitions | `0.5s` | Smooth, unhurried |
| Ambient float (orbs) | `20s` loop | Very slow, meditative |
| Blob morph | `8s` loop | Organic, living |
| Blob bounce | `3s` loop | Playful, toy-like |
| Pulse glow | `2s` loop | Gentle breathing |

### 8.3 Animation Patterns

**Blob bounce (playful floating):**
```css
@keyframes blob-bounce {
  0%, 100% { transform: translateY(0) scale(1); }
  50% { transform: translateY(-20px) scale(1.05); }
}
```

**Pulse glow (breathing light):**
```css
@keyframes pulse-glow {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.6; transform: scale(0.8); }
}
```

### 8.4 Performance Rules

- Use `transform` and `opacity` only for animations
- Avoid animating `width`, `height`, `top`, `left` — causes reflow
- Add `will-change: transform` on animated elements
- Respect `prefers-reduced-motion` — disable ambient animations for accessibility

---

## 9. Iconography

### 9.1 Style

- Inline SVG only — no icon libraries, no font icons
- 24×24px default, 18×18px for compact contexts
- 2px stroke width, round caps and joins
- Stroke color matches context:
  - Brand gradient context: `--cobalt` or gradient stroke
  - Secondary context: `--ink-muted`
  - Success: `#22c55e` (soft green, not harsh)

### 9.2 Common Icons

Standard inline SVGs for:
- Check / cross (feature lists)
- Arrow right (CTAs)
- Shield (security)
- Chart / graph (analytics)
- Users (teams)
- Zap (speed)
- Lock (privacy)
- Bell (alerts)
- Settings (gear)
- Plus / minus (expand/collapse)

---

## 10. Composition

Most layouts use **centered subjects** with lots of empty space. The backgrounds are simple gradients or aurora fields. This keeps the focus on the element's silhouette and glow.

The composition usually has:

- **one main subject** per section — clear hierarchy
- **minimal background** — aurora orbs, not busy patterns
- **shallow depth of field** — blurred backgrounds, sharp foreground
- **soft vignette** — edges gently fade
- **poster-like framing** — generous padding, intentional negative space

### 10.1 Page Structure

```
[Aurora background — fixed, full-screen, z-index 0]
[Nav — glass pill, fixed top, z-index 100]
[Hero — 100vh, centered, blob decorations]
[Section — max-width 1200px, centered, z-index 1]
  [Section header — eyebrow badge + title + subtitle]
  [Content grid — 3-col cards or 2-col features]
[Metrics bar — 4-col glass cards]
[CTA — centered, blob decorations]
[Footer — glass strip]
```

### 10.2 Grid

- Default: 3-column for cards, 2-column for features
- Gap: `20px` (`--s-5`)
- Max-width: `1200px`
- Mobile (`<= 768px`): single column, reduced padding

---

## 11. Component Patterns

### 11.1 Navigation

- Glass pill shape, fixed top, floating
- Logo: blob-morphing gradient circle + "AI Guardrail" in Space Grotesk
- Links: subtle gradient underline on hover
- CTA: jelly button (secondary glass variant)
- Backdrop blur creates separation from aurora background

### 11.2 Hero

- 100vh, flex centered, generous padding
- 3 bouncing blob decorations (pink, blue, lavender) — like floating toys
- Badge: glass pill with pulse dot (cyan glow)
- Title: gradient text on key phrase — "surprising you" in rainbow
- Subtitle: Inter, muted ink, warm and conversational
- CTA: jelly primary + glass secondary

### 11.3 Cards

- Glass background with blur backdrop
- Rainbow rim light at top (3px gradient border)
- Inset highlight gradient (subsurface scattering)
- Icon: gradient circle with SVG inside — like a toy button
- Hover: lift + scale + enhanced shadow — feels like picking up a jelly toy

### 11.4 Buttons

**Primary (jelly):**
- Rainbow gradient background (pink → lavender → blue)
- Cobalt text for contrast
- Pill shape (fully rounded)
- Spring hover animation — bounces when touched
- Shadow suggests floating above surface

**Secondary (glass):**
- Transparent background
- Glass border
- Ink-secondary text
- Lift on hover — less dramatic than primary

**Ghost:**
- No background
- Ink-muted text
- Subtle hover color change

### 11.5 Badges / Eyebrows

- Glass pill shape
- Uppercase, 12px, 600 weight, wide letter-spacing
- Cobalt text
- Examples: "USE CASES", "FEATURES", "WORKFLOW"
- Feel like **toy packaging labels** — clean, bold, friendly

### 11.6 Metrics

- Glass card container
- Gradient text for value (Space Grotesk, 40px, bold)
- Muted label below
- Top gradient accent line (rim light)
- Numbers feel like **scores on a collectible card**

### 11.7 Form Inputs (Auth Pages)

- Glass background
- Glass border, thicker on focus
- Pill shape or large radius
- Subtle glow on focus — `box-shadow: 0 0 0 3px rgba(196, 181, 255, 0.3)`
- Placeholder in `--ink-light`
- No harsh outlines — everything soft

---

## 12. Content Tone

- **Headlines:** bold, direct, benefit-driven — like toy packaging
- **Body:** conversational, no jargon — friendly and approachable
- **CTAs:** action-oriented, low friction — "Get started free", "See use cases"
- **Badges:** factual, not hype — "Now with multi-tenant workspaces"
- **No emojis** — use inline SVG icons instead
- **No all-caps shouting** — except eyebrow labels which are intentionally small and uppercase

---

## 13. Implementation Rules

### 13.1 CSS Architecture

- Use CSS custom properties (variables) for ALL tokens
- No hardcoded values in component CSS
- Prefer `px` for precise control (this is a visual-heavy design)
- Use `clamp()` for responsive typography only
- Keep animations in CSS, not JS — performance and simplicity

### 13.2 SvelteKit Specifics

- Scoped component styles where possible
- Global CSS for design tokens in `app.css`
- Inline SVG components for icons — no libraries
- `scroll-behavior: smooth` on html
- Respect `prefers-reduced-motion`

### 13.3 Accessibility

- Minimum contrast ratio: 4.5:1 for body text
- Focus states: visible soft glow, 2px offset, no harsh outlines
- `prefers-reduced-motion`: disable ambient animations (orbs, blob morph)
- Semantic HTML: nav, main, section, footer, article
- Alt text for any decorative images (though this design uses none)

### 13.4 Performance

- No external icon libraries (inline SVG only)
- Google Fonts: preconnect + display=swap
- Limit font weights to needed variants (load 2–3 weights max)
- `will-change` on animated elements only — remove after animation
- Backdrop filters are expensive — use sparingly on mobile

---

## 14. File Organization

```
design/
  index.html                    # Entry point → redirects to dreamcore-landing
  dreamcore-landing.html        # Marketing landing page
  dreamcore-pricing.html        # Pricing page
  dreamcore-signin.html         # Auth: sign in
  dreamcore-signup.html         # Auth: register
  dreamcore-forgot-password.html # Auth: password recovery
  dreamcore-dashboard.html      # App: overview/dashboard
  dreamcore-settings.html       # App: user settings
  dreamcore-team.html           # App: team management
  dreamcore-billing.html        # App: billing & usage
  dreamcore-guardrails.html     # App: policy configuration
  dreamcore-quality.html        # App: quality evaluations
  dreamcore-releases.html       # App: release tracking
  dreamcore-risk.html           # App: risk dashboard
  dreamcore-alerts.html         # App: alerts & incidents
  dreamcore-integrations.html   # App: provider integrations
  dreamcore-onboarding.html     # App: first-time wizard
  DESIGN_SYSTEM.md              # This file
  .github/
    workflows/
      pages.yml                 # GitHub Pages deployment
```

---

## 15. Design Formula

The style can be broken down like this:

> **cute/surreal subject + rounded toy shape + translucent jelly material + pastel holographic gradient + soft bloom lighting + minimal dreamy background**

That formula is the heart of the design.

Apply it to every component:
- Buttons are jelly blobs with rainbow gradients
- Cards are frosted glass with rim light
- Navigation is a floating glass pill
- Background is an aurora dreamscape
- Typography is bold and toy-like
- Motion is bouncy and breathing

---

## 16. Version History

| Version | Date | Changes |
|---|---|---|
| 1.0.0 | 2026-05-03 | Initial warm editorial system (Stripe + Linear) |
| 2.0.0 | 2026-05-03 | Dreamcore rewrite — pastel holographic, jelly materials, kawaii surrealism |

---

## 17. References

- **Live design repo:** https://github.com/khodex-rei/ai-guardrail-design
- **Deployed pages:** https://khodex-rei.github.io/ai-guardrail-design/
- **Dreamcore landing:** https://khodex-rei.github.io/ai-guardrail-design/dreamcore-landing.html
- **Dreamcore pricing:** https://khodex-rei.github.io/ai-guardrail-design/dreamcore-pricing.html
