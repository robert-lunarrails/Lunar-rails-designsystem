# 🚀 Lunar Rails — Design System & AI Context Guide
> Use this file as AI context when building any Lunar Rails product, page, or UI component.
> Drop this file as `CLAUDE.md` in your project root — it will be automatically read by Claude Code, Cursor, and most AI coding tools.

---

## 1. Brand Overview

| Field | Value |
|---|---|
| **Brand Name** | Lunar Rails |
| **Legal Entity** | OTC Services DMCC (Dubai) |
| **Tagline** | "Building Moonshots" |
| **Category** | Advanced Software Solutions — Blockchain & OTC Trading |
| **Core Services** | Blockchain Analytics, Lightning Technology, Software Development, Consulting |
| **Target Audience** | AML & Risk Companies, OTC Trading Firms, PSPs, Financial Institutions, BI Companies |

### Brand Personality
Bold · Technical · Professional · Visionary · Transparent

### Tone of Voice
- Write with **authority and precision** — this is a technical product for serious professionals
- **Never** use vague buzzwords or corporate-speak
- Be **direct and confident** — short sentences, active voice
- Occasionally use space/moon metaphors (`"launch"`, `"mission"`, `"moonshot"`) but sparingly
- Maintain **transparency** — explain what things do, not just what they are

---

## 2. Color System

### CSS Custom Properties (always use these tokens — never raw hex in components)

```css
:root {
  /* --- Primitives (reference only, do not use directly in UI) --- */
  --primitive-purple:       #7F21FF;
  --primitive-dark-purple:  #320065;
  --primitive-pink:         #FF569D;
  --primitive-yellow:       #FFBA0D;
  --primitive-magenta:      #D83CB9;
  --primitive-black:        #0A0A0A;
  --primitive-white:        #FFFFFF;

  /* --- Background Tokens --- */
  --color-bg-page:          #0A0A0A;   /* Page / outermost background */
  --color-bg-surface:       #111111;   /* Cards, panels, modals */
  --color-bg-elevated:      #1A1A1A;   /* Dropdowns, tooltips, hover states */
  --color-bg-overlay:       rgba(0, 0, 0, 0.75);

  /* --- Text Tokens --- */
  --color-text-primary:     #FFFFFF;
  --color-text-secondary:   #A0A0B0;
  --color-text-muted:       #5C5C72;
  --color-text-inverse:     #0A0A0A;

  /* --- Brand / Accent Tokens --- */
  --color-accent-primary:   #7F21FF;   /* Primary purple — CTAs, links, focus rings */
  --color-accent-pink:      #FF569D;   /* Secondary — highlights, tags, badges */
  --color-accent-yellow:    #FFBA0D;   /* Tertiary — warnings, stats, emphasis */
  --color-accent-magenta:   #D83CB9;   /* Decorative — gradients, hover glows */
  --color-accent-dark:      #320065;   /* Dark purple — deep bg accents, hero sections */

  /* --- Gradient Tokens --- */
  --gradient-brand:         linear-gradient(90deg, #7F21FF 0%, #FF569D 55%, #FFBA0D 100%);
  --gradient-brand-vertical:linear-gradient(180deg, #7F21FF 0%, #FF569D 55%, #FFBA0D 100%);
  --gradient-brand-radial:  radial-gradient(ellipse at top left, #7F21FF 0%, #320065 60%, #0A0A0A 100%);
  --gradient-glow-purple:   radial-gradient(circle, rgba(127,33,255,0.35) 0%, transparent 70%);
  --gradient-glow-pink:     radial-gradient(circle, rgba(255,86,157,0.25) 0%, transparent 70%);
  --gradient-page-hero:     radial-gradient(ellipse 80% 60% at 50% 0%, rgba(127,33,255,0.2) 0%, transparent 70%);

  /* --- Border Tokens --- */
  --color-border-subtle:    rgba(255, 255, 255, 0.06);
  --color-border-default:   rgba(255, 255, 255, 0.10);
  --color-border-strong:    rgba(255, 255, 255, 0.18);
  --color-border-accent:    rgba(127, 33, 255, 0.50);

  /* --- Semantic / State Tokens --- */
  --color-success:          #22C55E;
  --color-warning:          #FFBA0D;   /* reuses yellow */
  --color-error:            #EF4444;
  --color-info:             #7F21FF;   /* reuses purple */
}
```

### Usage Rules
- ✅ **Always** use CSS tokens — never hardcode `#7F21FF` directly in components
- ✅ The gradient `--gradient-brand` is the signature visual element — use it on hero text, CTAs, and key dividers
- ✅ All pages use a **dark background** — `--color-bg-page` is always `#0A0A0A`
- ❌ Never use white or light backgrounds — Lunar Rails is a dark-theme-only brand
- ❌ Never use more than 2 accent colors in a single UI section (outside of gradient elements)
- ❌ Never use the gradient on body text — display/hero headings only

---

## 3. Typography

### Font Stack

```css
/* Satoshi — sole brand typeface for all UI text */
@import url('https://api.fontshare.com/v2/css?f[]=satoshi@700,600,500,400,300&display=swap');

:root {
  --font-primary: 'Satoshi', sans-serif;   /* ALL text — headings, body, labels, UI */
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace; /* code, data, blockchain addresses */
}
```

### Type Scale

```css
:root {
  /* Display sizes */
  --text-hero:   clamp(48px, 8vw, 96px);   /* Hero headlines */
  --text-h1:     clamp(36px, 5vw, 64px);   /* Page titles */
  --text-h2:     clamp(28px, 4vw, 48px);   /* Section headings */
  --text-h3:     clamp(22px, 3vw, 32px);   /* Sub-section headings */
  --text-h4:     clamp(18px, 2.5vw, 24px); /* Card titles */
  --text-h5:     18px;                      /* List headings */

  /* Body sizes */
  --text-lg:     18px;  /* Lead text, feature descriptions */
  --text-base:   16px;  /* Body default */
  --text-sm:     14px;  /* Secondary text, captions */
  --text-xs:     12px;  /* Labels, metadata, legal */

  /* Weights */
  --weight-light:    300;
  --weight-regular:  400;
  --weight-medium:   500;
  --weight-semibold: 600;
  --weight-bold:     700;

  /* Leading */
  --leading-tight:  1.1;  /* Hero headlines */
  --leading-snug:   1.25; /* Headings */
  --leading-normal: 1.5;  /* Body text */
  --leading-relaxed:1.7;  /* Long-form descriptions */

  /* Tracking */
  --tracking-wide:   0.08em;  /* ALL CAPS labels */
  --tracking-tight:  -0.02em; /* Large display text */
}
```

### Typography Rules
- **Hero/H1**: Satoshi Bold, `--text-hero` / `--text-h1`, `--tracking-tight`, often gradient-filled via `background-clip: text`
- **H2–H3**: Satoshi Bold or Medium
- **Body & Descriptions**: Satoshi Regular or Light — Satoshi is the single typeface for all text
- **Labels & Tags**: Satoshi Medium or Semibold, uppercase, `--tracking-wide`
- **Code/Addresses**: JetBrains Mono (the only exception — monospace for technical data)
- ❌ Never use Montserrat, Inter, Roboto, or Arial — Satoshi is the exclusive brand typeface
- ❌ Never render gradient on body or small text — minimum size for gradient text is `--text-h3`

---

## 4. Spacing & Layout

```css
:root {
  /* --- Spacing Scale (8px base unit) --- */
  --space-1:   4px;
  --space-2:   8px;
  --space-3:   12px;
  --space-4:   16px;
  --space-5:   20px;
  --space-6:   24px;
  --space-8:   32px;
  --space-10:  40px;
  --space-12:  48px;
  --space-16:  64px;
  --space-20:  80px;
  --space-24:  96px;
  --space-32:  128px;

  /* --- Layout --- */
  --max-width-content:  1280px;
  --max-width-narrow:   800px;
  --page-padding-x:     clamp(24px, 5vw, 80px);
  --section-padding-y:  clamp(64px, 10vw, 128px);

  /* --- Border Radius --- */
  --radius-sm:    4px;   /* Badges, small tags */
  --radius-md:    8px;   /* Inputs, small buttons */
  --radius-lg:    12px;  /* Cards */
  --radius-xl:    16px;  /* Large cards, panels */
  --radius-2xl:   24px;  /* Feature cards */
  --radius-full:  9999px; /* Pills, avatar circles */

  /* --- Shadows --- */
  --shadow-sm:    0 1px 3px rgba(0,0,0,0.5);
  --shadow-md:    0 4px 16px rgba(0,0,0,0.5);
  --shadow-lg:    0 8px 40px rgba(0,0,0,0.6);
  --shadow-glow-purple: 0 0 40px rgba(127,33,255,0.4);
  --shadow-glow-pink:   0 0 30px rgba(255,86,157,0.3);
}
```

---

## 5. Component Patterns

### Buttons

```css
/* Base */
.btn {
  font-family: var(--font-primary);
  font-weight: var(--weight-semibold);
  font-size: var(--text-sm);
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  border-radius: var(--radius-md);
  padding: 12px 28px;
  border: none;
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.16, 1, 0.3, 1);
  position: relative;
  overflow: hidden;
}

/* Primary — gradient fill */
.btn-primary {
  background: var(--gradient-brand);
  color: white;
  box-shadow: var(--shadow-glow-purple);
}
.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 0 60px rgba(127,33,255,0.5);
}

/* Secondary — border only */
.btn-secondary {
  background: transparent;
  color: var(--color-text-primary);
  border: 1px solid var(--color-border-strong);
}
.btn-secondary:hover {
  border-color: var(--color-accent-primary);
  background: rgba(127,33,255,0.08);
}

/* Ghost */
.btn-ghost {
  background: transparent;
  color: var(--color-accent-pink);
  border: none;
  padding: 8px 0;
  text-decoration: underline;
  text-underline-offset: 4px;
}
```

### Cards

```css
.card {
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-xl);
  padding: var(--space-8);
  transition: border-color 250ms ease, box-shadow 250ms ease;
}
.card:hover {
  border-color: var(--color-border-accent);
  box-shadow: var(--shadow-glow-purple);
}

/* Featured/highlight card */
.card-featured {
  background: linear-gradient(135deg, rgba(127,33,255,0.12) 0%, rgba(50,0,101,0.3) 100%);
  border: 1px solid var(--color-border-accent);
}
```

### Inputs / Forms

```css
.input {
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-md);
  padding: 12px 16px;
  color: var(--color-text-primary);
  font-family: var(--font-primary);
  font-size: var(--text-base);
  width: 100%;
  transition: border-color 150ms ease;
  outline: none;
}
.input::placeholder { color: var(--color-text-muted); }
.input:focus {
  border-color: var(--color-accent-primary);
  box-shadow: 0 0 0 3px rgba(127,33,255,0.15);
}
```

### Gradient Text (Signature Pattern)

```css
.gradient-text {
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}
```

### Navigation

```css
/* Use dark/transparent nav on hero sections with video/gradient backgrounds */
.nav {
  background: rgba(10, 10, 10, 0.8);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--color-border-subtle);
  padding: var(--space-4) var(--page-padding-x);
  position: sticky;
  top: 0;
  z-index: 100;
}
```

### Stat / Counter Block

```css
/* Used in hero/section: "100M+", "5+ Years", etc. */
.stat-number {
  font-family: var(--font-primary);
  font-weight: var(--weight-bold);
  font-size: var(--text-h1);
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  line-height: var(--leading-tight);
}
.stat-label {
  font-family: var(--font-primary);
  color: var(--color-text-secondary);
  font-size: var(--text-sm);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wide);
}
```

### Divider / Accent Line

```css
.divider-brand {
  height: 1px;
  background: var(--gradient-brand);
  border: none;
  opacity: 0.4;
}
```

---

## 6. Motion & Animation

```css
:root {
  --ease-spring:     cubic-bezier(0.16, 1, 0.3, 1);   /* Snappy spring — all interactive elements */
  --ease-in-out:     cubic-bezier(0.4, 0, 0.2, 1);    /* Smooth transitions */
  --ease-out:        cubic-bezier(0, 0, 0.2, 1);       /* Exits, fades */

  --duration-fast:   150ms;   /* Hover states */
  --duration-base:   250ms;   /* Transitions, reveals */
  --duration-slow:   400ms;   /* Page elements, modals */
  --duration-hero:   800ms;   /* Hero entry animations */
}

/* Page entry — elements fade + rise from below */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Glow pulse for accent elements */
@keyframes glowPulse {
  0%, 100% { box-shadow: var(--shadow-glow-purple); }
  50%       { box-shadow: 0 0 60px rgba(127,33,255,0.7); }
}

/* Star / particle float */
@keyframes floatY {
  0%, 100% { transform: translateY(0px); }
  50%       { transform: translateY(-12px); }
}
```

### Motion Rules
- Entry animations use `fadeUp` with staggered `animation-delay` (100ms increments per element)
- Interactive elements always respond within `--duration-fast` (150ms) — never feel sluggish
- Glow effects on hover reinforce the neon/space aesthetic
- Video backgrounds (space footage, astronaut) are used in hero sections — always muted, autoplay, loop
- ❌ Never use `bounce` or elastic easing on forms or data elements
- ❌ Never animate more than 3 elements simultaneously

---

## 7. Visual Language & Imagery

### Approved Motifs
| Motif | Usage |
|---|---|
| 🌕 Moon | Hero sections, background texture, icon accents |
| 🚀 Rocket Ship | Product features, "launch" CTAs, loading states |
| 🤖 AI Robot | Technology sections, analytics features |
| 👨‍🚀 Astronaut | Hero video, brand photography |
| 🌌 Outer Space | Full-bleed backgrounds, section dividers |
| 🔷 Abstract Geometry | Background patterns, section overlays, cards |

### Aesthetic Direction
**Neon Cyberpunk × Space-Age Futuristic**

- Dark, near-black backgrounds with purple/pink ambient glow
- Glowing gradients used as light sources, not decoration
- Geometric abstract shapes as background texture (low opacity: 0.03–0.08)
- Purple/pink neon glow on interactive and featured elements
- Video backgrounds with space footage for hero sections

### Background Pattern
```css
/* Subtle grid overlay — apply to page or hero section */
.bg-grid {
  background-image:
    linear-gradient(rgba(127,33,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(127,33,255,0.03) 1px, transparent 1px);
  background-size: 64px 64px;
}

/* Noise texture for depth */
.bg-noise::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,..."); /* SVG noise */
  opacity: 0.03;
  pointer-events: none;
}
```

---

## 8. Page Anatomy

### Standard Page Structure
```
┌─────────────────────────────────────────┐
│  NAV (sticky, blur backdrop)            │
├─────────────────────────────────────────┤
│  HERO                                   │
│  • Full-screen (100vh)                  │
│  • Video background OR gradient bg      │
│  • H1 with gradient text                │
│  • Subtitle in Satoshi Light/Regular      │
│  • Primary CTA + Secondary CTA          │
│  • Partner logo strip                   │
├─────────────────────────────────────────┤
│  WHAT WE DO (feature grid)              │
│  • 3-column card layout                 │
│  • Icon + H4 + description per card     │
├─────────────────────────────────────────┤
│  STATS BAR                              │
│  • 4 gradient numbers across full width │
├─────────────────────────────────────────┤
│  WHO WE WORK WITH (audience section)    │
│  • 2-column or alternating layout       │
├─────────────────────────────────────────┤
│  FAQ (accordion)                        │
├─────────────────────────────────────────┤
│  CTA BANNER ("Ready to launch?")        │
│  • Full-width, gradient bg or glow      │
│  • Contact form                         │
├─────────────────────────────────────────┤
│  FOOTER                                 │
│  • Dark bg, logo, nav links             │
│  • Legal text (small, muted)            │
└─────────────────────────────────────────┘
```

---

## 9. Navigation Structure

```
LUNAR RAILS [logo]    Solutions ▾    Company    Blog    Contact    [CTA Button]
                      ┌──────────────────────────┐
                      │ Analytics Technology  →  │
                      │ Lightning Technology  →  │
                      └──────────────────────────┘
```

Footer columns: **Company** (Home, Analytics, Lightning, Company, Blog, Contact) | **Other Links** (FAQs, Careers, Terms, Privacy)

---

## 10. Do's and Don'ts for AI

### ✅ DO
- Use `--gradient-brand` on hero text, primary CTA buttons, and stat numbers
- Use `var(--color-bg-page)` (`#0A0A0A`) as the base background — always dark
- Use `Satoshi` for all text — it is the sole brand typeface across headings, body, and UI
- Add `backdrop-filter: blur()` on the nav bar and modals
- Use `fadeUp` with staggered delays for section/card entries
- Apply subtle purple glow (`--shadow-glow-purple`) on hover of cards and buttons
- Use grid or flex for layouts — always align to the spacing scale
- Keep copy bold and direct: "Launch", "Build", "Trace", "Analyse"
- Use `border: 1px solid var(--color-border-default)` on all cards

### ❌ DON'T
- Use light or white backgrounds — this is a dark-theme-only brand
- Use Montserrat, Inter, Roboto, Arial, or system-ui fonts — Satoshi is the only brand typeface
- Apply the brand gradient to body text, captions, or anything below `--text-h3`
- Use purple gradients on white/light surfaces (classic AI cliché)
- Use glassmorphism (frosted glass) as the primary UI pattern — reserve for nav only
- Hard-code hex values — always use CSS tokens
- Use more than 2 accent colors in a single section (outside of the linear gradient)
- Add drop shadows to text
- Use `border-radius` above `--radius-2xl` (24px) on non-pill elements
- Mix neon and pastel colors — the palette is dark + vivid, not soft

---

## 11. Key Copy & Messaging

| Context | Approved Copy |
|---|---|
| Hero headline | "Building Moonshots" |
| Hero sub | "Unlocking blockchain potential with cutting-edge software, analytics, and business intelligence." |
| CTA primary | "Get Started" / "Launch" / "Contact Us" |
| CTA secondary | "Learn More" |
| Footer CTA | "Ready to launch?" |
| Services | Analytics Technology · Lightning Technology · Software Development · Consulting & Cost Control |
| Legal | "OTC Services DMCC · DMCC License No. DMCC-400801 · Dubai, UAE" |

---

## 12. Tech Stack Preferences

When building Lunar Rails products, prefer:
- **React** (with TypeScript)
- **Tailwind CSS** or **CSS Modules** (map to the token system above)
- **Framer Motion** for animations
- **Next.js** for web applications
- **Recharts** or **D3** for blockchain data visualizations

---

*Last updated from: lunarrails.io website + official Brand Identity PDF*
*Use this file as the single source of truth for all Lunar Rails UI/UX decisions.*
