# 🚀 Lunar Ark — Design System & AI Context Guide
> Use this file as AI context when building any Lunar Ark product, page, or UI component.
> Drop this file as `CLAUDE.md` in your project root — it will be automatically read by Claude Code, Cursor, and most AI coding tools.

---

## 1. Brand Overview

| Field | Value |
|---|---|
| **Brand Name** | Lunar Ark |
| **Legal Entity** | Lunar Ark (UAE) |
| **Tagline** | "Reach Escape Velocity" |
| **Category** | Virtual Asset Trading — Premium OTC Services |
| **Core Services** | OTC Bitcoin Trading, Virtual Asset Management, Wealth Preservation, Compliance Advisory |
| **Target Audience** | High-net-worth individuals, institutional traders, OTC desks, wealth managers |
| **Regulatory** | Pursuing VARA approval (Virtual Assets Regulatory Authority, UAE) |
| **Website** | lunarark.ae |

### Brand Personality
Bold · Technical · Professional · Visionary · Transparent

### Tone of Voice
- Write with **authority and conviction** — this is premium financial services for serious investors
- Use **cosmic/escape velocity metaphors** — "launch", "escape", "orbit", "velocity" — these are on-brand
- Be **direct and confident** — declarative statements, no hedging, no jargon
- Maintain **transparency** around regulatory status and compliance
- Bitcoin-maximalist in tone — Bitcoin is "the most pristine, scarce and desirable asset in the known Universe"
- **Never** use vague fintech buzzwords without substance

---

## 2. Color System

### CSS Custom Properties (always use these tokens — never raw hex in components)

```css
:root {
  /* --- Primitives (reference only — never use directly in UI) --- */
  --primitive-indigo:       #330099;
  --primitive-violet:       #6D1EDD;
  --primitive-deep-navy:    #1F0955;
  --primitive-black:        #000000;
  --primitive-hot-pink:     #EA4A97;
  --primitive-white:        #FFFFFF;

  /* --- Background Tokens --- */
  --color-bg-page:          #000000;   /* Page / outermost background */
  --color-bg-surface:       #0A0412;   /* Cards, panels, modals */
  --color-bg-elevated:      #130826;   /* Dropdowns, tooltips, hover states */
  --color-bg-deep:          #1F0955;   /* Deep navy — hero sections, feature areas */
  --color-bg-overlay:       rgba(0, 0, 0, 0.8);

  /* --- Text Tokens --- */
  --color-text-primary:     #FFFFFF;
  --color-text-secondary:   #A89EC0;   /* Muted purple-toned white */
  --color-text-muted:       #5E4D80;
  --color-text-inverse:     #000000;

  /* --- Brand / Accent Tokens --- */
  --color-accent-primary:   #6D1EDD;   /* Violet — CTAs, links, focus rings */
  --color-accent-indigo:    #330099;   /* Indigo — secondary accents */
  --color-accent-pink:      #EA4A97;   /* Hot Pink — highlights, tags, badges */
  --color-accent-deep:      #1F0955;   /* Deep Navy — dark sections */

  /* --- Gradient Tokens --- */
  --gradient-brand:         linear-gradient(90deg, #EA4A97 0%, #6D1EDD 100%);
  --gradient-brand-diagonal:linear-gradient(135deg, #EA4A97 0%, #6D1EDD 60%, #330099 100%);
  --gradient-brand-vertical:linear-gradient(180deg, #EA4A97 0%, #6D1EDD 100%);
  --gradient-deep:          linear-gradient(180deg, #000000 0%, #1F0955 50%, #330099 100%);
  --gradient-glow-violet:   radial-gradient(circle, rgba(109,30,221,0.4) 0%, transparent 70%);
  --gradient-glow-pink:     radial-gradient(circle, rgba(234,74,151,0.3) 0%, transparent 70%);
  --gradient-page-hero:     radial-gradient(ellipse 80% 60% at 50% 0%, rgba(109,30,221,0.25) 0%, transparent 70%);

  /* --- Border Tokens --- */
  --color-border-subtle:    rgba(109, 30, 221, 0.12);
  --color-border-default:   rgba(109, 30, 221, 0.25);
  --color-border-strong:    rgba(109, 30, 221, 0.45);
  --color-border-pink:      rgba(234, 74, 151, 0.40);

  /* --- Semantic / State Tokens --- */
  --color-success:          #22C55E;
  --color-warning:          #EA4A97;   /* reuses hot pink */
  --color-error:            #EF4444;
  --color-info:             #6D1EDD;   /* reuses violet */

  /* --- Metallic Silver (gradient) --- */
  --gradient-silver:        linear-gradient(135deg, #C0C0C0 0%, #E8E8E8 40%, #A8A8A8 70%, #D4D4D4 100%);
}
```

### Usage Rules
- ✅ **Always** use CSS tokens — never hardcode `#6D1EDD` directly in components
- ✅ The gradient `--gradient-brand` (Pink → Violet) is the signature visual element
- ✅ All pages use a **black or deep navy background** — never white or light
- ✅ The metallic silver gradient is used sparingly on premium accent elements
- ❌ Never use white or light backgrounds — Lunar Ark is dark-theme-only
- ❌ Never use more than 2 accent colors in a single UI section (outside gradient elements)
- ❌ Never apply the brand gradient to body text — display/hero headings only

---

## 3. Typography

### Font Stack

```css
/* Barlow — primary brand typeface (Condensed + Semi Condensed variants) */
@import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;500;600;700&family=Barlow+Semi+Condensed:wght@300;400;500;600;700&family=Barlow:wght@300;400;500;600;700&display=swap');

:root {
  --font-display:   'Barlow Condensed', sans-serif;       /* Hero, headings, nav — ALL CAPS preferred */
  --font-body:      'Barlow Semi Condensed', sans-serif;  /* Body text, descriptions, UI */
  --font-regular:   'Barlow', sans-serif;                 /* Standard body, long-form */
  --font-mono:      'JetBrains Mono', 'Fira Code', monospace; /* code, addresses, data */
}
```

### Type Scale

```css
:root {
  /* Display sizes */
  --text-hero:   clamp(56px, 10vw, 120px);  /* Hero headlines — Condensed, ALL CAPS */
  --text-h1:     clamp(40px, 6vw, 80px);    /* Page titles */
  --text-h2:     clamp(28px, 4vw, 52px);    /* Section headings */
  --text-h3:     clamp(22px, 3vw, 36px);    /* Sub-section headings */
  --text-h4:     clamp(18px, 2.5vw, 26px);  /* Card titles */
  --text-h5:     18px;                       /* List headings */

  /* Body sizes */
  --text-lg:     20px;  /* Lead text */
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
  --leading-tight:   1.0;  /* Hero — very tight, condensed feel */
  --leading-snug:    1.2;  /* Headings */
  --leading-normal:  1.5;  /* Body text */
  --leading-relaxed: 1.75; /* Long-form */

  /* Tracking */
  --tracking-widest: 0.20em;  /* ALL CAPS hero, labels */
  --tracking-wide:   0.10em;  /* Uppercase nav, buttons */
  --tracking-tight:  -0.01em; /* Large condensed display text */
}
```

### Typography Rules
- **Hero/H1**: Barlow Condensed Bold · ALL CAPS · `--text-hero` · `--tracking-widest`
- **H2–H3**: Barlow Condensed Bold or Medium · uppercase preferred for section headings
- **Body & Descriptions**: Barlow Semi Condensed Regular or Light
- **Labels & Tags**: Barlow Condensed Semibold · uppercase · `--tracking-wide`
- **Code/Addresses**: JetBrains Mono (only exception — monospace for technical data)
- ✅ ALL CAPS is a key brand expression — use liberally on headings and navigation
- ❌ Never use Inter, Roboto, Arial, or Satoshi — Barlow family is the exclusive brand typeface
- ❌ Never render gradient on text below `--text-h3`

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
  --section-padding-y:  clamp(80px, 12vw, 160px);

  /* --- Border Radius --- */
  --radius-sm:    2px;    /* Sharp — Barlow condensed, technical feel */
  --radius-md:    4px;    /* Inputs, small buttons */
  --radius-lg:    8px;    /* Cards */
  --radius-xl:    12px;   /* Large cards, panels */
  --radius-2xl:   20px;   /* Feature cards */
  --radius-full:  9999px; /* Pills */

  /* --- Shadows --- */
  --shadow-sm:          0 1px 4px rgba(0,0,0,0.8);
  --shadow-md:          0 4px 20px rgba(0,0,0,0.8);
  --shadow-lg:          0 8px 48px rgba(0,0,0,0.9);
  --shadow-glow-violet: 0 0 40px rgba(109,30,221,0.5);
  --shadow-glow-pink:   0 0 30px rgba(234,74,151,0.4);
}
```

> **Radius note:** Lunar Ark uses sharper corners than typical brands — the condensed, technical aesthetic calls for `--radius-sm` (2px) to `--radius-lg` (8px) on most elements.

---

## 5. Component Patterns

### Buttons

```css
.btn {
  font-family: var(--font-display);
  font-weight: var(--weight-semibold);
  font-size: var(--text-sm);
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  border-radius: var(--radius-md);
  padding: 12px 32px;
  cursor: pointer;
  transition: all 200ms cubic-bezier(0.16, 1, 0.3, 1);
}

/* Primary — gradient fill */
.btn-primary {
  background: var(--gradient-brand);
  color: white;
  border: none;
  box-shadow: var(--shadow-glow-violet);
}
.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 0 60px rgba(109,30,221,0.6);
}

/* Secondary — border only */
.btn-secondary {
  background: transparent;
  color: var(--color-text-primary);
  border: 1px solid var(--color-border-strong);
}
.btn-secondary:hover {
  border-color: var(--color-accent-pink);
  background: rgba(109,30,221,0.1);
}

/* Ghost / text link */
.btn-ghost {
  background: transparent;
  color: var(--color-accent-pink);
  border: none;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
.btn-ghost::after { content: '→'; transition: transform 150ms ease; }
.btn-ghost:hover::after { transform: translateX(4px); }
```

### Cards

```css
.card {
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-lg);
  padding: var(--space-8);
  transition: border-color 250ms ease, box-shadow 250ms ease;
}
.card:hover {
  border-color: var(--color-border-strong);
  box-shadow: var(--shadow-glow-violet);
}

/* Featured card — deep navy bg */
.card-featured {
  background: linear-gradient(135deg, rgba(109,30,221,0.15) 0%, rgba(31,9,85,0.4) 100%);
  border: 1px solid var(--color-border-strong);
}
```

### Inputs

```css
.input {
  background: rgba(109,30,221,0.05);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-md);
  padding: 12px 16px;
  color: var(--color-text-primary);
  font-family: var(--font-body);
  font-size: var(--text-base);
  width: 100%;
  transition: border-color 150ms ease;
  outline: none;
}
.input::placeholder { color: var(--color-text-muted); }
.input:focus {
  border-color: var(--color-accent-primary);
  box-shadow: 0 0 0 3px rgba(109,30,221,0.15);
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
.nav {
  background: rgba(0, 0, 0, 0.9);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--color-border-subtle);
  padding: var(--space-4) var(--page-padding-x);
  position: sticky;
  top: 0;
  z-index: 100;
  font-family: var(--font-display);
  text-transform: uppercase;
  letter-spacing: var(--tracking-wide);
}
```

### Stat / Counter Block

```css
.stat-number {
  font-family: var(--font-display);
  font-weight: var(--weight-bold);
  font-size: var(--text-h1);
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  line-height: var(--leading-tight);
}
.stat-label {
  font-family: var(--font-body);
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
  opacity: 0.35;
}
```

---

## 6. Motion & Animation

```css
:root {
  --ease-spring:     cubic-bezier(0.16, 1, 0.3, 1);
  --ease-in-out:     cubic-bezier(0.4, 0, 0.2, 1);
  --ease-out:        cubic-bezier(0, 0, 0.2, 1);

  --duration-fast:   150ms;
  --duration-base:   250ms;
  --duration-slow:   400ms;
  --duration-hero:   900ms;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes glowPulse {
  0%, 100% { box-shadow: var(--shadow-glow-violet); }
  50%       { box-shadow: 0 0 80px rgba(109,30,221,0.7); }
}

@keyframes floatY {
  0%, 100% { transform: translateY(0px); }
  50%       { transform: translateY(-14px); }
}
```

### Motion Rules
- Entry animations use `fadeUp` with staggered `animation-delay` (120ms per element)
- Interactive elements respond within `--duration-fast` (150ms)
- Glow pulse on hero CTAs and featured elements
- Video backgrounds (space, cosmic footage): always muted, autoplay, loop
- ❌ Never use bounce or elastic easing on financial UI elements
- ❌ Never animate more than 3 elements simultaneously

---

## 7. Visual Language & Imagery

### Approved Motifs
| Motif | Usage |
|---|---|
| 🌕 Moon | Logo brandmark, hero sections, section accents |
| 🚀 Rocket / Launch | Hero, CTA sections, "escape velocity" narrative |
| 👨‍🚀 Astronaut | Brand photography, hero background |
| 🌌 Outer Space | Full-bleed video/image backgrounds |
| ⚡ Futuristic / Space-Age | Technology sections, product features |
| ₿ Bitcoin | Core product — can use as visual motif |

### Aesthetic Direction
**Deep Space Premium — Dark Luxury × Cosmic Futurism**

- Pure black page backgrounds with deep violet/indigo atmosphere
- The arc/orbit shape from the brandmark is a recurring geometric motif
- Metallic silver gradient used on premium accent elements only
- Hot pink (`#EA4A97`) as a high-energy highlight against the dark palette
- Video backgrounds: cosmic space footage, futuristic movement
- Typography set in ALL CAPS with wide tracking for impact

### Background Patterns

```css
/* Subtle radial deep space atmosphere */
.bg-deep-space {
  background:
    radial-gradient(ellipse 60% 50% at 30% 20%, rgba(109,30,221,0.08) 0%, transparent 60%),
    radial-gradient(ellipse 40% 40% at 70% 80%, rgba(234,74,151,0.05) 0%, transparent 60%),
    #000000;
}

/* Subtle grid — technical data feel */
.bg-grid {
  background-image:
    linear-gradient(rgba(109,30,221,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(109,30,221,0.04) 1px, transparent 1px);
  background-size: 48px 48px;
}
```

---

## 8. Logo Usage

### Inversed Logo (primary — for dark backgrounds)
- White fill on dark/black backgrounds
- SVG source: `Lunar_Ark_Inversed_Logo.svg`
- The arc/orbit mark above the wordmark is the brandmark

### Full Logo (for light contexts only)
- Deep navy fill (`#1F0955`)
- SVG source: `Lunar_Ark_Logo_Full.svg`
- Only use on white/light background contexts

### Logo Rules
- ✅ Use inversed (white) logo on all dark UI backgrounds
- ✅ Minimum clear space: equal to the height of the arc mark on all sides
- ❌ Never apply the gradient fill directly to the logo
- ❌ Never distort, rotate, or recolor the logo outside of the two approved versions

---

## 9. Page Anatomy

### Standard Page Structure
```
┌─────────────────────────────────────────────┐
│  NAV (sticky · blur · ALL CAPS links)        │
├─────────────────────────────────────────────┤
│  HERO                                        │
│  ├─ Full-screen (100vh)                      │
│  ├─ Video or deep space background           │
│  ├─ H1 ALL CAPS — "REACH ESCAPE VELOCITY"    │
│  ├─ Subtitle — Barlow Semi Condensed Light   │
│  ├─ Primary CTA + Secondary CTA              │
│  └─ Trust badges (VARA, ISO 27001, CFCS)     │
├─────────────────────────────────────────────┤
│  BITCOIN SECTION                             │
│  └─ 5-point narrative with numbered items    │
├─────────────────────────────────────────────┤
│  QUOTES / SOCIAL PROOF                       │
│  └─ Large pull quotes — Saylor, Gates, etc.  │
├─────────────────────────────────────────────┤
│  TRUST / COMPLIANCE                          │
│  └─ VARA · ISO 27001 · CFCS partner          │
├─────────────────────────────────────────────┤
│  EXPERTISE / OUR OFFER                       │
│  └─ OTC trading · Virtual assets · Security  │
├─────────────────────────────────────────────┤
│  FAQ  (accordion)                            │
├─────────────────────────────────────────────┤
│  CTA BANNER — "ALL ABOARD. BUCKLE UP!"       │
│  └─ gradient bg · Start Trading CTA          │
├─────────────────────────────────────────────┤
│  FOOTER                                      │
│  └─ Logo · Company links · Other links       │
│  └─ VARA disclaimer · Legal                  │
└─────────────────────────────────────────────┘
```

---

## 10. Navigation Structure

```
LUNAR ARK [logo]    OTC TRADING    COMPANY    FAQ    [START TRADING →]
```

**Footer columns:**
- **Company** — Home · OTC Trading · Company · Start Trading · FAQs
- **Other Links** — Terms of Use · Privacy Policy · Public Disclosure · Risk Disclosure · Virtual Assets Offered · Virtual Assets Standards · Complaints Procedure

---

## 11. Do's and Don'ts for AI

### ✅ DO
- Use ALL CAPS for all headings, hero text, and navigation links
- Use `--gradient-brand` (Pink → Violet) on hero text, primary CTAs, and stat numbers
- Use `var(--color-bg-page)` (`#000000`) as the base background — always pure black
- Use Barlow Condensed for headings and Barlow Semi Condensed for body
- Add `backdrop-filter: blur()` on nav and modals
- Apply `--shadow-glow-violet` on hover for cards and buttons
- Use `fadeUp` with staggered delays for section entry animations
- Use wide letter-spacing (`--tracking-widest`) on all hero and heading text
- Use the arc/orbit shape motif from the logo as a decorative element
- Keep borders sharp — use `--radius-sm` to `--radius-lg` (2px–8px), never rounded
- Reference Bitcoin directly and confidently — it is the core product

### ❌ DON'T
- Use white or light backgrounds — dark-theme-only brand
- Use Inter, Roboto, Arial, Satoshi, or any non-Barlow font
- Apply gradient to body text or anything below `--text-h3`
- Use lowercase for headings — ALL CAPS is the brand standard
- Use purple gradients on light backgrounds
- Hard-code hex values — always use CSS tokens
- Use `border-radius` above `--radius-2xl` (20px) on non-pill elements
- Mix pink and violet accents randomly — gradient flows from pink (left/top) to violet (right/bottom)
- Use glassmorphism as primary pattern — reserve for nav only
- Add drop shadows to text

---

## 12. Key Copy & Messaging

| Context | Approved Copy |
|---------|---------------|
| Hero headline | `"REACH ESCAPE VELOCITY"` |
| Hero subtitle | `"Onboard to the new era of Virtual Assets Management"` |
| CTA primary | `"START TRADING"` |
| CTA secondary | `"LEARN MORE"` |
| Section CTA | `"ALL ABOARD. BUCKLE UP!"` |
| Bitcoin tagline | `"The most pristine, scarce and desirable asset in the known Universe."` |
| Mission | `"Secure and private trading tailored for high-volume cryptocurrency transactions"` |
| Footer CTA | `"Secure and private trading tailored for high-volume cryptocurrency transactions, ensuring efficiency and protecting client confidentiality."` |
| Legal disclaimer | `"We are securing the necessary approvals. More updates coming soon."` |
| Regulatory | `"Currently pursuing approval from VARA (Virtual Assets Regulatory Authority)"` |

---

## 13. Tech Stack Preferences

When building Lunar Ark products, prefer:
- **React** (with TypeScript)
- **Tailwind CSS** or **CSS Modules** (map to token system above)
- **Framer Motion** for animations
- **Next.js** for web applications
- **Recharts** or **D3** for trading/price data visualizations

---

*Last updated from: lunarark.ae website + official Brand Identity PDF + SVG logos*
*Use this file as the single source of truth for all Lunar Ark UI/UX decisions.*
