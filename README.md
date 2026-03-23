<div align="center">

<!-- Hero Banner using GitHub-compatible SVG -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=7F21FF,FF569D,FFBA0D&height=200&section=header&text=LUNAR%20RAILS&fontSize=52&fontColor=ffffff&fontAlignY=38&desc=Design%20System%20%26%20AI%20Context%20Guide&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>

<br/>

<!-- Badges -->
![Version](https://img.shields.io/badge/version-1.0.0-7F21FF?style=for-the-badge&logoColor=white)
![Font](https://img.shields.io/badge/font-Satoshi-FF569D?style=for-the-badge&logoColor=white)
![Theme](https://img.shields.io/badge/theme-Dark%20Only-0A0A0A?style=for-the-badge&logoColor=white)
![Stack](https://img.shields.io/badge/stack-React%20%2B%20Next.js-FFBA0D?style=for-the-badge&logoColor=black)
![Website](https://img.shields.io/badge/website-lunarrails.io-7F21FF?style=for-the-badge&logo=globe&logoColor=white)

<br/>

> **Drop `CLAUDE.md` into your project root** — Claude Code, Cursor, and most AI coding tools will automatically read it as persistent brand context for every UI decision.

</div>

---

## 📖 Table of Contents

- [Brand Overview](#-brand-overview)
- [Color System](#-color-system)
- [Typography](#-typography)
- [Spacing & Layout](#-spacing--layout)
- [Component Patterns](#-component-patterns)
- [Motion & Animation](#-motion--animation)
- [Visual Language](#-visual-language--imagery)
- [Page Anatomy](#-page-anatomy)
- [AI Rules — Do's & Don'ts](#-dos-and-donts-for-ai)
- [Copy & Messaging](#-key-copy--messaging)
- [Tech Stack](#-tech-stack)

---

## 🚀 Brand Overview

<table>
<tr><td><b>Brand Name</b></td><td>Lunar Rails</td></tr>
<tr><td><b>Legal Entity</b></td><td>OTC Services DMCC (Dubai)</td></tr>
<tr><td><b>Tagline</b></td><td><i>"Building Moonshots"</i></td></tr>
<tr><td><b>Category</b></td><td>Advanced Software Solutions — Blockchain & OTC Trading</td></tr>
<tr><td><b>Core Services</b></td><td>Blockchain Analytics · Lightning Technology · Software Development · Consulting</td></tr>
<tr><td><b>Audience</b></td><td>AML & Risk Companies · OTC Traders · PSPs · Financial Institutions · BI Companies</td></tr>
<tr><td><b>Website</b></td><td><a href="https://www.lunarrails.io">lunarrails.io</a></td></tr>
</table>

### Brand Personality

```
Bold  ·  Technical  ·  Professional  ·  Visionary  ·  Transparent
```

### Tone of Voice

| Principle | Guidance |
|---|---|
| ✍️ Authority | Write with precision — this is a technical product for serious professionals |
| 🎯 Direct | Short sentences, active voice, no vague buzzwords or corporate-speak |
| 🌕 Metaphors | Space/moon language (`"launch"`, `"mission"`, `"moonshot"`) — use sparingly |
| 🔍 Transparent | Explain what things *do*, not just what they *are* |

---

## 🎨 Color System

> **Rule:** Always use CSS tokens. Never hardcode hex values in components.

### Palette at a Glance

| Swatch | Token | Hex | Usage |
|--------|-------|-----|-------|
| ![#7F21FF](https://placehold.co/18x18/7F21FF/7F21FF.png) | `--color-accent-primary` | `#7F21FF` | CTAs, links, focus rings |
| ![#320065](https://placehold.co/18x18/320065/320065.png) | `--color-accent-dark` | `#320065` | Hero bg accents, deep sections |
| ![#FF569D](https://placehold.co/18x18/FF569D/FF569D.png) | `--color-accent-pink` | `#FF569D` | Highlights, tags, badges |
| ![#FFBA0D](https://placehold.co/18x18/FFBA0D/FFBA0D.png) | `--color-accent-yellow` | `#FFBA0D` | Warnings, stats, emphasis |
| ![#D83CB9](https://placehold.co/18x18/D83CB9/D83CB9.png) | `--color-accent-magenta` | `#D83CB9` | Decorative, hover glows |
| ![#0A0A0A](https://placehold.co/18x18/0A0A0A/0A0A0A.png) | `--color-bg-page` | `#0A0A0A` | Page background (always dark) |
| ![#111111](https://placehold.co/18x18/111111/111111.png) | `--color-bg-surface` | `#111111` | Cards, panels, modals |
| ![#1A1A1A](https://placehold.co/18x18/1A1A1A/1A1A1A.png) | `--color-bg-elevated` | `#1A1A1A` | Dropdowns, tooltips |

### Signature Gradient

```
Purple ────────────────────── Pink ─────────── Yellow
#7F21FF                      #FF569D           #FFBA0D
   0%                          55%               100%
```

### Full CSS Token Map

```css
:root {
  /* --- Primitives (reference only — never use directly in UI) --- */
  --primitive-purple:       #7F21FF;
  --primitive-dark-purple:  #320065;
  --primitive-pink:         #FF569D;
  --primitive-yellow:       #FFBA0D;
  --primitive-magenta:      #D83CB9;

  /* --- Backgrounds --- */
  --color-bg-page:          #0A0A0A;   /* Page / outermost background */
  --color-bg-surface:       #111111;   /* Cards, panels, modals */
  --color-bg-elevated:      #1A1A1A;   /* Dropdowns, tooltips, hover states */
  --color-bg-overlay:       rgba(0, 0, 0, 0.75);

  /* --- Text --- */
  --color-text-primary:     #FFFFFF;
  --color-text-secondary:   #A0A0B0;
  --color-text-muted:       #5C5C72;
  --color-text-inverse:     #0A0A0A;

  /* --- Accents --- */
  --color-accent-primary:   #7F21FF;
  --color-accent-pink:      #FF569D;
  --color-accent-yellow:    #FFBA0D;
  --color-accent-magenta:   #D83CB9;
  --color-accent-dark:      #320065;

  /* --- Gradients --- */
  --gradient-brand:          linear-gradient(90deg, #7F21FF 0%, #FF569D 55%, #FFBA0D 100%);
  --gradient-brand-vertical: linear-gradient(180deg, #7F21FF 0%, #FF569D 55%, #FFBA0D 100%);
  --gradient-brand-radial:   radial-gradient(ellipse at top left, #7F21FF 0%, #320065 60%, #0A0A0A 100%);
  --gradient-glow-purple:    radial-gradient(circle, rgba(127,33,255,0.35) 0%, transparent 70%);
  --gradient-glow-pink:      radial-gradient(circle, rgba(255,86,157,0.25) 0%, transparent 70%);
  --gradient-page-hero:      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(127,33,255,0.2) 0%, transparent 70%);

  /* --- Borders --- */
  --color-border-subtle:    rgba(255, 255, 255, 0.06);
  --color-border-default:   rgba(255, 255, 255, 0.10);
  --color-border-strong:    rgba(255, 255, 255, 0.18);
  --color-border-accent:    rgba(127, 33, 255, 0.50);

  /* --- Semantic States --- */
  --color-success:          #22C55E;
  --color-warning:          #FFBA0D;
  --color-error:            #EF4444;
  --color-info:             #7F21FF;
}
```

### Color Rules

| | Rule |
|---|---|
| ✅ | Always use CSS tokens — never hardcode `#7F21FF` directly |
| ✅ | `--gradient-brand` is the signature element — use on hero text, CTAs, dividers |
| ✅ | All pages use `--color-bg-page` (`#0A0A0A`) — always dark |
| ❌ | Never use white or light backgrounds |
| ❌ | Never use more than 2 accent colors per section (outside gradient elements) |
| ❌ | Never apply gradient to body text — hero/display headings only |

---

## 🔤 Typography

> **Satoshi is the sole brand typeface.** It covers all roles — headings, body, labels, UI text. No secondary font.

### Import

```css
/* Satoshi — sole brand typeface for all UI text */
@import url('https://api.fontshare.com/v2/css?f[]=satoshi@700,600,500,400,300&display=swap');

:root {
  --font-primary: 'Satoshi', sans-serif;   /* ALL text — headings, body, labels, UI */
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace; /* code, data, blockchain addresses only */
}
```

### Type Scale

| Token | Value | Role |
|-------|-------|------|
| `--text-hero` | `clamp(48px, 8vw, 96px)` | Hero headlines |
| `--text-h1` | `clamp(36px, 5vw, 64px)` | Page titles |
| `--text-h2` | `clamp(28px, 4vw, 48px)` | Section headings |
| `--text-h3` | `clamp(22px, 3vw, 32px)` | Sub-section headings |
| `--text-h4` | `clamp(18px, 2.5vw, 24px)` | Card titles |
| `--text-h5` | `18px` | List headings |
| `--text-lg` | `18px` | Lead text, feature descriptions |
| `--text-base` | `16px` | Body default |
| `--text-sm` | `14px` | Secondary text, captions |
| `--text-xs` | `12px` | Labels, metadata, legal |

### Weight Scale

| Token | Value | Use |
|-------|-------|-----|
| `--weight-light` | `300` | Long-form body, subtitles |
| `--weight-regular` | `400` | Standard body |
| `--weight-medium` | `500` | UI elements, nav links |
| `--weight-semibold` | `600` | Labels, buttons, CTAs |
| `--weight-bold` | `700` | Headings, display |

### Usage by Role

| Element | Spec |
|---------|------|
| **Hero / H1** | Satoshi Bold · `--text-hero` · `--tracking-tight` · gradient fill via `background-clip: text` |
| **H2 – H3** | Satoshi Bold or Medium |
| **Body & Descriptions** | Satoshi Regular or Light |
| **Labels & Tags** | Satoshi Semibold · uppercase · `--tracking-wide` |
| **Code / Blockchain Addresses** | JetBrains Mono — the only exception |

### Typography Rules

| | Rule |
|---|---|
| ❌ | Never use Montserrat, Inter, Roboto, or Arial — Satoshi is the **exclusive** brand typeface |
| ❌ | Never apply gradient to text below `--text-h3` |
| ✅ | Gradient text minimum size: `--text-h3` (32px) |
| ✅ | `letter-spacing: --tracking-tight` on hero text |
| ✅ | `letter-spacing: --tracking-wide` on uppercase labels |

---

## 📐 Spacing & Layout

### Spacing Scale — 8px Base Unit

| Token | Value | Token | Value |
|-------|-------|-------|-------|
| `--space-1` | `4px` | `--space-10` | `40px` |
| `--space-2` | `8px` | `--space-12` | `48px` |
| `--space-3` | `12px` | `--space-16` | `64px` |
| `--space-4` | `16px` | `--space-20` | `80px` |
| `--space-5` | `20px` | `--space-24` | `96px` |
| `--space-6` | `24px` | `--space-32` | `128px` |
| `--space-8` | `32px` | | |

### Layout Tokens

```css
:root {
  --max-width-content:  1280px;
  --max-width-narrow:   800px;
  --page-padding-x:     clamp(24px, 5vw, 80px);
  --section-padding-y:  clamp(64px, 10vw, 128px);
}
```

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `--radius-sm` | `4px` | Badges, small tags |
| `--radius-md` | `8px` | Inputs, small buttons |
| `--radius-lg` | `12px` | Cards |
| `--radius-xl` | `16px` | Large cards, panels |
| `--radius-2xl` | `24px` | Feature cards |
| `--radius-full` | `9999px` | Pills, avatar circles |

### Shadow & Glow

```css
--shadow-sm:          0 1px 3px rgba(0,0,0,0.5);
--shadow-md:          0 4px 16px rgba(0,0,0,0.5);
--shadow-lg:          0 8px 40px rgba(0,0,0,0.6);
--shadow-glow-purple: 0 0 40px rgba(127,33,255,0.4);   /* cards, buttons on hover */
--shadow-glow-pink:   0 0 30px rgba(255,86,157,0.3);   /* secondary hover accents */
```

---

## 🧩 Component Patterns

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
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.16, 1, 0.3, 1);
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

/* Featured card */
.card-featured {
  background: linear-gradient(135deg, rgba(127,33,255,0.12) 0%, rgba(50,0,101,0.3) 100%);
  border: 1px solid var(--color-border-accent);
}
```

### Inputs

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
}
.input:focus {
  border-color: var(--color-accent-primary);
  box-shadow: 0 0 0 3px rgba(127,33,255,0.15);
  outline: none;
}
```

### Gradient Text — Signature Pattern

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

### Brand Divider

```css
.divider-brand {
  height: 1px;
  background: var(--gradient-brand);
  border: none;
  opacity: 0.4;
}
```

---

## ✨ Motion & Animation

### Timing Tokens

```css
:root {
  --ease-spring:     cubic-bezier(0.16, 1, 0.3, 1);  /* Snappy spring — all interactive elements */
  --ease-in-out:     cubic-bezier(0.4, 0, 0.2, 1);   /* Smooth transitions */
  --ease-out:        cubic-bezier(0, 0, 0.2, 1);      /* Exits, fades */

  --duration-fast:   150ms;   /* Hover states */
  --duration-base:   250ms;   /* Transitions, reveals */
  --duration-slow:   400ms;   /* Page elements, modals */
  --duration-hero:   800ms;   /* Hero entry animations */
}
```

### Keyframes

```css
/* Page entry — fade + rise */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Glow pulse — accent elements */
@keyframes glowPulse {
  0%, 100% { box-shadow: var(--shadow-glow-purple); }
  50%       { box-shadow: 0 0 60px rgba(127,33,255,0.7); }
}

/* Float — decorative elements */
@keyframes floatY {
  0%, 100% { transform: translateY(0px); }
  50%       { transform: translateY(-12px); }
}
```

### Motion Rules

| | Rule |
|---|---|
| ✅ | Section/card entries use `fadeUp` with staggered `animation-delay` (100ms per element) |
| ✅ | Interactive elements respond within `--duration-fast` (150ms) — never sluggish |
| ✅ | Glow on hover reinforces the neon/space aesthetic |
| ✅ | Hero video backgrounds: always `muted`, `autoplay`, `loop`, space footage |
| ❌ | Never use `bounce` or elastic easing on forms or data components |
| ❌ | Never animate more than 3 elements simultaneously |

---

## 🌌 Visual Language & Imagery

### Aesthetic Direction

> **Neon Cyberpunk × Space-Age Futuristic**

- Dark, near-black backgrounds with purple/pink ambient glow
- Glowing gradients used as **light sources**, not decoration
- Geometric abstract shapes as background texture at low opacity (`0.03–0.08`)
- Purple/pink neon glow on interactive and featured elements
- Video backgrounds with space footage for hero sections

### Approved Visual Motifs

| Motif | Usage |
|-------|-------|
| 🌕 Moon | Hero sections, background texture, icon accents |
| 🚀 Rocket Ship | Product features, "launch" CTAs, loading states |
| 🤖 AI Robot | Technology sections, analytics features |
| 👨‍🚀 Astronaut | Hero video, brand photography |
| 🌌 Outer Space | Full-bleed backgrounds, section dividers |
| 🔷 Abstract Geometry | Background patterns, section overlays, cards |

### Background Patterns

```css
/* Subtle purple grid overlay */
.bg-grid {
  background-image:
    linear-gradient(rgba(127,33,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(127,33,255,0.03) 1px, transparent 1px);
  background-size: 64px 64px;
}

/* Noise texture layer */
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

## 🗺️ Page Anatomy

### Standard Page Structure

```
┌─────────────────────────────────────────────┐
│  NAV  (sticky · blur backdrop · z-100)       │
├─────────────────────────────────────────────┤
│  HERO                                        │
│  ├─ Full-screen (100vh)                      │
│  ├─ Video background OR gradient bg          │
│  ├─ H1 with gradient text                    │
│  ├─ Subtitle in Satoshi Light/Regular        │
│  ├─ Primary CTA + Secondary CTA              │
│  └─ Partner logo strip                       │
├─────────────────────────────────────────────┤
│  WHAT WE DO  (feature grid)                  │
│  └─ 3-column · Icon + H4 + description       │
├─────────────────────────────────────────────┤
│  STATS BAR                                   │
│  └─ 4 gradient numbers · full width          │
├─────────────────────────────────────────────┤
│  WHO WE WORK WITH                            │
│  └─ 2-column or alternating layout           │
├─────────────────────────────────────────────┤
│  FAQ  (accordion)                            │
├─────────────────────────────────────────────┤
│  CTA BANNER  — "Ready to launch?"            │
│  └─ Full-width · gradient bg · contact form  │
├─────────────────────────────────────────────┤
│  FOOTER                                      │
│  └─ Dark bg · logo · nav links · legal       │
└─────────────────────────────────────────────┘
```

### Navigation Structure

```
☾ LUNAR RAILS     Solutions ▾     Company     Blog     Contact     [ Launch → ]
                  ┌──────────────────────────────┐
                  │  Analytics Technology    →   │
                  │  Lightning Technology    →   │
                  └──────────────────────────────┘
```

**Footer columns:**
- **Company** — Home · Analytics · Lightning · Company · Blog · Contact
- **Other Links** — FAQs · Careers · Terms of Use · Privacy Policy

---

## ✅ Do's and Don'ts for AI

### ✅ DO

- Use `--gradient-brand` on hero text, primary CTA buttons, and stat numbers
- Use `var(--color-bg-page)` (`#0A0A0A`) as the base background — always dark
- Use `Satoshi` for all text — it is the sole brand typeface across headings, body, and UI
- Add `backdrop-filter: blur()` on the nav bar and modals
- Use `fadeUp` with staggered `animation-delay` for section and card entries
- Apply `--shadow-glow-purple` on hover states for cards and buttons
- Use grid or flex for layouts — always align to the spacing scale
- Keep copy bold and direct: `"Launch"` · `"Build"` · `"Trace"` · `"Analyse"`
- Use `border: 1px solid var(--color-border-default)` on all cards

### ❌ DON'T

- Use light or white backgrounds — this is a **dark-theme-only** brand
- Use Montserrat, Inter, Roboto, Arial, or system-ui — Satoshi is the only brand typeface
- Apply the brand gradient to body text, captions, or anything below `--text-h3`
- Use purple gradients on white/light surfaces (classic AI cliché)
- Use glassmorphism as the primary UI pattern — reserve for nav only
- Hard-code hex values — always use CSS tokens
- Use more than 2 accent colors in a single section (outside of gradient elements)
- Add drop shadows to text
- Use `border-radius` above `--radius-2xl` (24px) on non-pill elements
- Mix neon and pastel colors — the palette is dark + vivid, never soft

---

## 💬 Key Copy & Messaging

| Context | Approved Copy |
|---------|---------------|
| Hero headline | `"Building Moonshots"` |
| Hero subtitle | `"Unlocking blockchain potential with cutting-edge software, analytics, and business intelligence."` |
| CTA primary | `"Get Started"` · `"Launch"` · `"Contact Us"` |
| CTA secondary | `"Learn More"` |
| Footer CTA | `"Ready to launch?"` |
| Services | `Analytics Technology · Lightning Technology · Software Development · Consulting & Cost Control` |
| Legal | `OTC Services DMCC · DMCC License No. DMCC-400801 · Dubai, UAE` |

---

## 🛠️ Tech Stack

| Layer | Preferred |
|-------|-----------|
| **Framework** | React (TypeScript) + Next.js |
| **Styling** | Tailwind CSS or CSS Modules — map to token system above |
| **Animation** | Framer Motion |
| **Data Viz** | Recharts or D3 (blockchain/analytics data) |
| **Font** | Satoshi via [Fontshare](https://www.fontshare.com/fonts/satoshi) |
| **Mono Font** | JetBrains Mono (code/addresses only) |

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=7F21FF,FF569D,FFBA0D&height=100&section=footer&reversal=true" width="100%"/>

**Lunar Rails Design System** · Built for AI-assisted development  
*Source: [lunarrails.io](https://www.lunarrails.io) + Official Brand Identity PDF*

![Made with](https://img.shields.io/badge/maintained%20by-Lunar%20Rails-7F21FF?style=flat-square)
![License](https://img.shields.io/badge/internal%20use-only-FF569D?style=flat-square)

</div>
