<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=EA4A97,6D1EDD,330099&height=200&section=header&text=LUNAR%20ARK&fontSize=58&fontColor=ffffff&fontAlignY=38&desc=Design%20System%20%26%20AI%20Context%20Guide&descAlignY=60&descSize=17&animation=fadeIn" width="100%"/>

<br/>

![Version](https://img.shields.io/badge/version-1.0.0-6D1EDD?style=for-the-badge&logoColor=white)
![Font](https://img.shields.io/badge/font-Barlow%20Condensed-EA4A97?style=for-the-badge&logoColor=white)
![Theme](https://img.shields.io/badge/theme-Dark%20Only-000000?style=for-the-badge&logoColor=white)
![Stack](https://img.shields.io/badge/stack-React%20%2B%20Next.js-330099?style=for-the-badge&logoColor=white)
![Website](https://img.shields.io/badge/website-lunarark.ae-6D1EDD?style=for-the-badge&logo=globe&logoColor=white)

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
- [Logo Usage](#-logo-usage)
- [Page Anatomy](#-page-anatomy)
- [AI Rules — Do's & Don'ts](#-dos-and-donts-for-ai)
- [Copy & Messaging](#-key-copy--messaging)
- [Tech Stack](#-tech-stack)

---

## 🚀 Brand Overview

<table>
<tr><td><b>Brand Name</b></td><td>Lunar Ark</td></tr>
<tr><td><b>Legal Entity</b></td><td>Lunar Ark (UAE)</td></tr>
<tr><td><b>Tagline</b></td><td><i>"Reach Escape Velocity"</i></td></tr>
<tr><td><b>Category</b></td><td>Virtual Asset Trading — Premium OTC Services</td></tr>
<tr><td><b>Core Services</b></td><td>OTC Bitcoin Trading · Virtual Asset Management · Wealth Preservation · Compliance Advisory</td></tr>
<tr><td><b>Audience</b></td><td>HNW Individuals · Institutional Traders · OTC Desks · Wealth Managers</td></tr>
<tr><td><b>Regulatory</b></td><td>Pursuing VARA approval — Virtual Assets Regulatory Authority, UAE</td></tr>
<tr><td><b>Website</b></td><td><a href="https://www.lunarark.ae">lunarark.ae</a></td></tr>
</table>

### Brand Personality

```
Bold  ·  Technical  ·  Professional  ·  Visionary  ·  Transparent
```

### Tone of Voice

| Principle | Guidance |
|---|---|
| 🌌 Cosmic | Use escape velocity metaphors: "launch", "orbit", "escape", "velocity" |
| ✍️ Conviction | Bold, declarative statements — no hedging, no jargon |
| ₿ Bitcoin-first | Bitcoin is "the most pristine, scarce and desirable asset in the known Universe" |
| 🔍 Transparent | Be clear about VARA regulatory status and compliance posture |
| 🔠 ALL CAPS | Headings and navigation in ALL CAPS — it's a core brand expression |

---

## 🎨 Color System

> **Rule:** Always use CSS tokens. Never hardcode hex values in components.

### Palette at a Glance

| Swatch | Token | Hex | Usage |
|--------|-------|-----|-------|
| ![#6D1EDD](https://placehold.co/18x18/6D1EDD/6D1EDD.png) | `--color-accent-primary` | `#6D1EDD` | CTAs, links, focus rings |
| ![#330099](https://placehold.co/18x18/330099/330099.png) | `--color-accent-indigo` | `#330099` | Indigo — secondary accents |
| ![#1F0955](https://placehold.co/18x18/1F0955/1F0955.png) | `--color-bg-deep` | `#1F0955` | Deep navy — hero bg, feature areas |
| ![#EA4A97](https://placehold.co/18x18/EA4A97/EA4A97.png) | `--color-accent-pink` | `#EA4A97` | Hot Pink — highlights, tags, CTAs |
| ![#000000](https://placehold.co/18x18/000000/000000.png) | `--color-bg-page` | `#000000` | Page background (always black) |
| ![#0A0412](https://placehold.co/18x18/0A0412/0A0412.png) | `--color-bg-surface` | `#0A0412` | Cards, panels, modals |
| ![#A89EC0](https://placehold.co/18x18/A89EC0/A89EC0.png) | `--color-text-secondary` | `#A89EC0` | Muted purple-toned body text |

### Signature Gradient

```
Hot Pink ──────────────────────────────── Violet
#EA4A97                                  #6D1EDD
   0%                                      100%
```

### Full CSS Token Map

```css
:root {
  /* --- Primitives (reference only) --- */
  --primitive-indigo:       #330099;
  --primitive-violet:       #6D1EDD;
  --primitive-deep-navy:    #1F0955;
  --primitive-black:        #000000;
  --primitive-hot-pink:     #EA4A97;

  /* --- Backgrounds --- */
  --color-bg-page:          #000000;
  --color-bg-surface:       #0A0412;
  --color-bg-elevated:      #130826;
  --color-bg-deep:          #1F0955;
  --color-bg-overlay:       rgba(0, 0, 0, 0.8);

  /* --- Text --- */
  --color-text-primary:     #FFFFFF;
  --color-text-secondary:   #A89EC0;
  --color-text-muted:       #5E4D80;

  /* --- Accents --- */
  --color-accent-primary:   #6D1EDD;
  --color-accent-indigo:    #330099;
  --color-accent-pink:      #EA4A97;
  --color-accent-deep:      #1F0955;

  /* --- Gradients --- */
  --gradient-brand:          linear-gradient(90deg, #EA4A97 0%, #6D1EDD 100%);
  --gradient-brand-diagonal: linear-gradient(135deg, #EA4A97 0%, #6D1EDD 60%, #330099 100%);
  --gradient-deep:           linear-gradient(180deg, #000000 0%, #1F0955 50%, #330099 100%);
  --gradient-glow-violet:    radial-gradient(circle, rgba(109,30,221,0.4) 0%, transparent 70%);
  --gradient-glow-pink:      radial-gradient(circle, rgba(234,74,151,0.3) 0%, transparent 70%);
  --gradient-silver:         linear-gradient(135deg, #C0C0C0 0%, #E8E8E8 40%, #A8A8A8 70%, #D4D4D4 100%);

  /* --- Borders --- */
  --color-border-subtle:    rgba(109, 30, 221, 0.12);
  --color-border-default:   rgba(109, 30, 221, 0.25);
  --color-border-strong:    rgba(109, 30, 221, 0.45);
  --color-border-pink:      rgba(234, 74, 151, 0.40);

  /* --- Semantic States --- */
  --color-success:          #22C55E;
  --color-error:            #EF4444;
  --color-warning:          #EA4A97;
  --color-info:             #6D1EDD;
}
```

### Color Rules

| | Rule |
|---|---|
| ✅ | Always use CSS tokens — never hardcode hex values |
| ✅ | `--gradient-brand` (Pink → Violet) is the signature gradient |
| ✅ | Page background is always `#000000` — pure black |
| ✅ | Metallic silver gradient used sparingly on premium accents only |
| ❌ | Never use white or light backgrounds |
| ❌ | Never use more than 2 accents per section (outside gradients) |
| ❌ | Gradient flows Pink (left/start) → Violet (right/end) — never reverse |

---

## 🔤 Typography

> **Barlow is the sole brand typeface family.** Condensed for headings (ALL CAPS), Semi Condensed for body. No external fonts.

### Import

```css
@import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;500;600;700&family=Barlow+Semi+Condensed:wght@300;400;500;600;700&family=Barlow:wght@300;400;500;600;700&display=swap');

:root {
  --font-display:  'Barlow Condensed', sans-serif;       /* Headings, nav, hero — ALL CAPS */
  --font-body:     'Barlow Semi Condensed', sans-serif;  /* Body text, descriptions, UI */
  --font-regular:  'Barlow', sans-serif;                 /* Standard body, long-form */
  --font-mono:     'JetBrains Mono', 'Fira Code', monospace; /* code, addresses only */
}
```

### Type Scale

| Token | Value | Role |
|-------|-------|------|
| `--text-hero` | `clamp(56px, 10vw, 120px)` | Hero — ALL CAPS, Condensed Bold |
| `--text-h1` | `clamp(40px, 6vw, 80px)` | Page titles |
| `--text-h2` | `clamp(28px, 4vw, 52px)` | Section headings |
| `--text-h3` | `clamp(22px, 3vw, 36px)` | Sub-section headings |
| `--text-h4` | `clamp(18px, 2.5vw, 26px)` | Card titles |
| `--text-lg` | `20px` | Lead text |
| `--text-base` | `16px` | Body default |
| `--text-sm` | `14px` | Secondary text, captions |
| `--text-xs` | `12px` | Labels, metadata, legal |

### Usage by Role

| Element | Spec |
|---------|------|
| **Hero / H1** | Barlow Condensed Bold · ALL CAPS · `--text-hero` · `--tracking-widest` |
| **H2 – H3** | Barlow Condensed Bold or Medium · uppercase |
| **Body** | Barlow Semi Condensed Regular or Light |
| **Labels & Tags** | Barlow Condensed Semibold · uppercase · `--tracking-wide` |
| **Code / Addresses** | JetBrains Mono — only exception |

### Typography Rules

| | Rule |
|---|---|
| ✅ | ALL CAPS on all headings and nav links — core brand expression |
| ✅ | Wide letter-spacing (`--tracking-widest`) on hero and display text |
| ❌ | Never use Inter, Roboto, Arial, Satoshi — Barlow family only |
| ❌ | Never apply gradient below `--text-h3` |
| ❌ | Never use sentence case or lowercase for headings |

---

## 📐 Spacing & Layout

### Spacing Scale — 8px Base Unit

| Token | Value | Token | Value |
|-------|-------|-------|-------|
| `--space-1` | `4px` | `--space-10` | `40px` |
| `--space-2` | `8px` | `--space-12` | `48px` |
| `--space-3` | `12px` | `--space-16` | `64px` |
| `--space-4` | `16px` | `--space-20` | `80px` |
| `--space-6` | `24px` | `--space-24` | `96px` |
| `--space-8` | `32px` | `--space-32` | `128px` |

### Border Radius — Sharp & Technical

| Token | Value | Usage |
|-------|-------|-------|
| `--radius-sm` | `2px` | Badges, tags — very sharp |
| `--radius-md` | `4px` | Inputs, buttons |
| `--radius-lg` | `8px` | Cards |
| `--radius-xl` | `12px` | Large cards, panels |
| `--radius-2xl` | `20px` | Feature cards (max) |
| `--radius-full` | `9999px` | Pills only |

> Lunar Ark uses **sharper corners** than typical brands — the condensed, technical aesthetic favors 2px–8px.

### Shadow & Glow

```css
--shadow-glow-violet: 0 0 40px rgba(109,30,221,0.5);
--shadow-glow-pink:   0 0 30px rgba(234,74,151,0.4);
```

---

## 🧩 Component Patterns

### Buttons

```css
.btn {
  font-family: var(--font-display);
  font-weight: var(--weight-semibold);
  letter-spacing: var(--tracking-wide);
  text-transform: uppercase;
  border-radius: var(--radius-md);
  padding: 12px 32px;
}
.btn-primary  { background: var(--gradient-brand); box-shadow: var(--shadow-glow-violet); }
.btn-secondary{ border: 1px solid var(--color-border-strong); background: transparent; }
.btn-ghost    { color: var(--color-accent-pink); } /* with → arrow */
```

### Cards

```css
.card { background: var(--color-bg-surface); border: 1px solid var(--color-border-default); border-radius: var(--radius-lg); }
.card:hover  { border-color: var(--color-border-strong); box-shadow: var(--shadow-glow-violet); }
.card-featured { background: linear-gradient(135deg, rgba(109,30,221,0.15) 0%, rgba(31,9,85,0.4) 100%); }
```

### Gradient Text

```css
.gradient-text {
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

---

## ✨ Motion & Animation

### Timing Tokens

| Token | Value | Use |
|-------|-------|-----|
| `--duration-fast` | `150ms` | Hover states |
| `--duration-base` | `250ms` | Transitions, reveals |
| `--duration-slow` | `400ms` | Page elements, modals |
| `--duration-hero` | `900ms` | Hero entry |
| `--ease-spring` | `cubic-bezier(.16,1,.3,1)` | All interactive |

### Rules

| | Rule |
|---|---|
| ✅ | `fadeUp` with 120ms staggered delays for section entries |
| ✅ | `glowPulse` on hero CTAs and featured elements |
| ✅ | Video backgrounds: cosmic space · muted · autoplay · loop |
| ❌ | No bounce or elastic easing on financial UI |
| ❌ | No more than 3 simultaneous animations |

---

## 🌌 Visual Language & Imagery

### Aesthetic Direction

> **Deep Space Premium — Dark Luxury × Cosmic Futurism**

- Pure black page with deep violet/indigo atmospheric glow
- The **arc/orbit shape** from the brandmark is a recurring geometric motif
- Metallic silver gradient used sparingly on premium accents
- Hot pink (`#EA4A97`) as high-energy highlight against the deep palette
- ALL CAPS typography with wide tracking creates a confident, commanding presence
- Bitcoin-forward — use ₿ symbolism, price data, and scarcity narrative

### Approved Motifs

| Motif | Usage |
|-------|-------|
| 🌕 Moon | Logo mark, hero sections, section accents |
| 🚀 Rocket / Launch | Hero, "escape velocity" narrative, CTAs |
| 👨‍🚀 Astronaut | Brand photography, hero backgrounds |
| 🌌 Outer Space | Full-bleed video/image backgrounds |
| ₿ Bitcoin | Core product — use as visual motif freely |
| ⚡ Futuristic / Space-Age | Technology, compliance sections |

---

## 🔖 Logo Usage

| Version | File | Background | Fill |
|---------|------|------------|------|
| **Inversed (primary)** | `Lunar_Ark_Inversed_Logo.svg` | Dark / Black | White |
| **Full** | `Lunar_Ark_Logo_Full.svg` | Light / White | Deep Navy `#1F0955` |

**Logo Rules:**
- ✅ Always use the **inversed (white) logo** on dark UI
- ✅ Minimum clear space = height of arc mark on all sides
- ❌ Never apply gradient fill to the logo
- ❌ Never distort, rotate, or recolor outside approved versions

---

## 🗺️ Page Anatomy

```
┌─────────────────────────────────────────────┐
│  NAV  (sticky · blur · ALL CAPS links)       │
├─────────────────────────────────────────────┤
│  HERO                                        │
│  ├─ 100vh · video or deep space bg           │
│  ├─ H1 ALL CAPS — "REACH ESCAPE VELOCITY"    │
│  ├─ Subtitle — Barlow Semi Condensed Light   │
│  ├─ "START TRADING" + "LEARN MORE" CTAs      │
│  └─ Trust badges — VARA · ISO 27001 · CFCS   │
├─────────────────────────────────────────────┤
│  BITCOIN SECTION                             │
│  └─ 5-point numbered narrative               │
├─────────────────────────────────────────────┤
│  SOCIAL PROOF / QUOTES                       │
│  └─ Large pull quotes — Saylor, Gates, etc.  │
├─────────────────────────────────────────────┤
│  TRUST & COMPLIANCE                          │
│  └─ VARA · ISO 27001 · CFCS                  │
├─────────────────────────────────────────────┤
│  EXPERTISE / OUR OFFER                       │
│  └─ OTC · Virtual Assets · Security          │
├─────────────────────────────────────────────┤
│  FAQ  (accordion)                            │
├─────────────────────────────────────────────┤
│  CTA BANNER — "ALL ABOARD. BUCKLE UP!"       │
├─────────────────────────────────────────────┤
│  FOOTER                                      │
│  └─ Logo · Company · Links · Legal           │
│  └─ VARA disclaimer                          │
└─────────────────────────────────────────────┘
```

**Nav:** `LUNAR ARK [logo]` · `OTC TRADING` · `COMPANY` · `FAQ` · `[START TRADING →]`

**Footer columns:** Company (Home · OTC Trading · Company · Start Trading · FAQs) | Other Links (Terms · Privacy · Public Disclosure · Risk Disclosure · Virtual Assets Offered · Standards · Complaints)

---

## ✅ Do's and Don'ts for AI

### ✅ DO

- Use ALL CAPS for all headings, hero text, and navigation links
- Use `--gradient-brand` (Pink → Violet) on hero text, CTAs, and stat numbers
- Use `var(--color-bg-page)` (`#000000`) as base background — always pure black
- Use Barlow Condensed for headings and Barlow Semi Condensed for body text
- Add `backdrop-filter: blur()` on nav and modals
- Apply `--shadow-glow-violet` on hover for cards and buttons
- Use sharp corners — `--radius-sm` to `--radius-lg` (2–8px)
- Use wide letter-spacing on all hero and heading text
- Reference Bitcoin directly and confidently — it's the core product
- Use the arc/orbit motif from the logo as a recurring decorative element

### ❌ DON'T

- Use white or light backgrounds — dark-theme-only brand
- Use Inter, Roboto, Arial, Satoshi, or any non-Barlow font
- Apply gradient to body text or anything below `--text-h3`
- Use lowercase or sentence case for headings — ALL CAPS is the standard
- Use excessively rounded corners (`--radius-2xl` is the maximum)
- Hard-code hex values — always use CSS tokens
- Mix pink and violet randomly — gradient always flows Pink → Violet
- Use glassmorphism as primary pattern — nav backdrop-blur only
- Add drop shadows to text
- Use more than 2 accent colors in a single section

---

## 💬 Key Copy & Messaging

| Context | Approved Copy |
|---------|---------------|
| Hero Headline | `"REACH ESCAPE VELOCITY"` |
| Hero Subtitle | `"Onboard to the new era of Virtual Assets Management"` |
| CTA Primary | `"START TRADING"` |
| CTA Secondary | `"LEARN MORE"` |
| Section Banner | `"ALL ABOARD. BUCKLE UP!"` |
| Bitcoin | `"The most pristine, scarce and desirable asset in the known Universe."` |
| Expertise | `"Lunar Ark simplifies the purchase, sale, and swap of virtual assets while aligning with the regulatory framework of VARA in the UAE."` |
| Legal | `"© 2024 Lunar Ark · All rights reserved · We are securing the necessary approvals."` |

---

## 🛠️ Tech Stack

| Layer | Preferred |
|-------|-----------|
| **Framework** | React (TypeScript) + Next.js |
| **Styling** | Tailwind CSS or CSS Modules |
| **Animation** | Framer Motion |
| **Data Viz** | Recharts or D3 (trading/price data) |
| **Display Font** | Barlow Condensed via Google Fonts |
| **Body Font** | Barlow Semi Condensed via Google Fonts |
| **Mono Font** | JetBrains Mono (code/addresses only) |

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=EA4A97,6D1EDD,330099&height=100&section=footer&reversal=true" width="100%"/>

**Lunar Ark Design System** · Built for AI-assisted development
*Source: [lunarark.ae](https://www.lunarark.ae) + Official Brand Identity PDF + SVG Logos*

![Maintained by](https://img.shields.io/badge/maintained%20by-Lunar%20Ark-6D1EDD?style=flat-square)
![License](https://img.shields.io/badge/internal%20use-only-EA4A97?style=flat-square)

</div>
