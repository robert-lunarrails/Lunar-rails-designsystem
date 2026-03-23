<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=6C2DB7,4D73D8&height=180&section=header&text=40ACRES&fontSize=60&fontColor=ffffff&fontAlignY=38&desc=Design%20System%20%26%20AI%20Context%20Guide&descAlignY=60&descSize=17&animation=fadeIn" width="100%"/>

<br/>

![Version](https://img.shields.io/badge/version-1.0.0-342E51?style=for-the-badge&logoColor=white)
![Font](https://img.shields.io/badge/font-Degular-6C2DB7?style=for-the-badge&logoColor=white)
![Theme](https://img.shields.io/badge/theme-Light%20Mode-FFFFFF?style=for-the-badge&color=E7EBF7&logoColor=342E51)
![Stack](https://img.shields.io/badge/stack-React%20%2B%20Next.js-4D73D8?style=for-the-badge&logoColor=white)
![Website](https://img.shields.io/badge/website-40acres.pro-6C2DB7?style=for-the-badge&logo=globe&logoColor=white)

<br/>

> **Drop `CLAUDE.md` in your project root** — Claude Code, Cursor, and most AI tools read it as persistent brand context.

</div>

---

## 📖 Table of Contents

- [Brand Architecture](#-brand-architecture)
- [Design Philosophy](#-core-design-philosophy)
- [Color System](#-color-system)
- [Typography](#-typography)
- [Spacing & Layout](#-spacing--layout)
- [Components](#-component-patterns)
- [Visual Language](#-visual-language)
- [Logo Usage](#-logo-usage)
- [Page Anatomy](#-page-anatomy)
- [AI Rules](#-dos-and-donts-for-ai)
- [Copy & Messaging](#-key-copy--messaging)
- [Tech Stack](#-tech-stack)

---

## 🏗️ Brand Architecture

<table>
<tr><td><b>Brand</b></td><td>40Acres</td></tr>
<tr><td><b>Legal Entity</b></td><td>40 Acres, S.A. de C.V. — El Salvador</td></tr>
<tr><td><b>Registration</b></td><td>No. 2024113630</td></tr>
<tr><td><b>BTC License</b></td><td>664bd64379e50005ac479693</td></tr>
<tr><td><b>DASP License</b></td><td>PSAD-0046</td></tr>
<tr><td><b>Tagline</b></td><td><i>"Financial Freedom with Bitcoin"</i></td></tr>
<tr><td><b>Website</b></td><td><a href="https://www.40acres.pro">40acres.pro</a></td></tr>
</table>

### Child Brands

| Brand | Purpose |
|-------|---------|
| `[4N]` **40Node** | Enterprise Lightning Network node infrastructure |
| `[4S]` **40Swap** | Bitcoin swap gateway — fast, secure, simple |

### Brand Personality

```
Revolutionary  ·  Bold  ·  Visionary  ·  Transparent
```

---

## 🎯 Core Design Philosophy

> **40Acres is a light-mode, editorial brand.**

The website is primarily **white and light grey**. Hero sections use **full-bleed photography or video** — not dark backgrounds, not gradient atmospheres. The violet/blue gradient is reserved exclusively for **CTA buttons**.

### The gradient — exactly where it belongs

| Context | Use gradient? |
|---------|--------------|
| Primary CTA buttons | ✅ Yes — vertical, 0px border-radius |
| Hero headings | ❌ No — white text on photo |
| Section headings | ❌ No — `#342E51` on white/grey |
| Backgrounds | ❌ No |
| Decorative elements | ❌ No |

---

## 🎨 Color System

> White and grey backgrounds dominate. Violet is a spot accent, not an atmosphere.

### Palette

| Swatch | Token | Hex | Usage |
|--------|-------|-----|-------|
| ![#6C2DB7](https://placehold.co/18x18/6C2DB7/6C2DB7.png) | `--color-accent-primary` | `#6C2DB7` | Violet — links, icons, active states |
| ![#4D73D8](https://placehold.co/18x18/4D73D8/4D73D8.png) | `--color-accent-blue` | `#4D73D8` | Blue — gradient endpoint only |
| ![#342E51](https://placehold.co/18x18/342E51/342E51.png) | `--color-text-primary` | `#342E51` | Logo Black — all text on light bg |
| ![#201C32](https://placehold.co/18x18/201C32/201C32.png) | `--color-bg-dark` | `#201C32` | Footer and dark CTA bands only |
| ![#E7EBF7](https://placehold.co/18x18/E7EBF7/E7EBF7.png) | `--color-bg-section` | `#E7EBF7` | Alternating light grey sections |
| ![#FFFFFF](https://placehold.co/18x18/FFFFFF/FFFFFF.png) | `--color-bg-page` | `#FFFFFF` | Default page background |

### Button Gradient

```
Top: #6C2DB7 (Violet)
         ↓ vertical
Bottom: #4D73D8 (Blue)

direction: 180deg
border-radius: 0  ← sharp corners, brand standard
```

### Full CSS Token Map

```css
:root {
  /* Backgrounds */
  --color-bg-page:       #FFFFFF;
  --color-bg-section:    #E7EBF7;
  --color-bg-dark:       #201C32;
  --color-bg-elevated:   #342E51;

  /* Text */
  --color-text-primary:  #342E51;
  --color-text-secondary:#5A5070;
  --color-text-muted:    #8C85A6;
  --color-text-on-dark:  #FFFFFF;
  --color-text-on-photo: #FFFFFF;

  /* Accents */
  --color-accent-primary:#6C2DB7;
  --color-accent-blue:   #4D73D8;

  /* Gradient — buttons only */
  --gradient-btn: linear-gradient(180deg, #6C2DB7 0%, #4D73D8 100%);

  /* Borders */
  --color-border-default: rgba(52, 46, 81, 0.15);
  --color-border-strong:  rgba(52, 46, 81, 0.35);
  --color-border-accent:  rgba(108, 45, 183, 0.35);
}
```

### Color Rules

| | Rule |
|---|---|
| ✅ | Default page background is white — **light-mode brand** |
| ✅ | `--gradient-btn` on buttons only — **vertical, 0px border-radius** |
| ✅ | Headings on light: `#342E51` · on photo: white |
| ❌ | Never gradient on text, backgrounds, or any non-button element |
| ❌ | Dark background only in footer and specific CTA bands |

---

## 🔤 Typography

> Degular is the sole brand typeface. Commercial font — self-host. Use `DM Sans` as fallback for prototypes.

### Font Stack

```css
:root {
  --font-primary: 'Degular', 'DM Sans', system-ui, sans-serif;
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace;
}
```

### Type Scale

| Token | Value | Role |
|-------|-------|------|
| `--text-hero` | `clamp(48px, 8vw, 96px)` | Hero — white, on photography |
| `--text-h1` | `clamp(36px, 5vw, 64px)` | Page titles — `#342E51` |
| `--text-h2` | `clamp(26px, 3.5vw, 44px)` | Section headings |
| `--text-h3` | `clamp(20px, 2.5vw, 32px)` | Sub-sections |
| `--text-h4` | `clamp(16px, 2vw, 22px)` | Card titles |
| `--text-base` | `16px` | Body default |
| `--text-sm` | `14px` | Captions, labels |
| `--text-xs` | `12px` | Legal, metadata |

### Usage by Context

| Element | Spec |
|---------|------|
| **Hero heading (on photo)** | Degular Bold · white · **no gradient** |
| **H1–H2 on white/grey** | Degular Bold · `#342E51` |
| **Body text** | Degular Light/Regular · `--color-text-secondary` |
| **Nav links** | Degular Medium · `#342E51` |
| **CTA labels** | Degular Medium · white |
| **Labels** | Degular Medium · uppercase · `--tracking-wide` |
| **Code / BTC addresses** | JetBrains Mono — only exception |

---

## 📐 Spacing & Layout

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `--radius-sm` | `4px` | Inputs, form elements |
| `--radius-md` | `8px` | Secondary buttons |
| `--radius-lg` | `12px` | Cards |
| `--radius-xl` | `16px` | Large panels |
| `--radius-full` | `9999px` | Pills, tags |
| **0px** | — | **Primary buttons — brand standard** |

---

## 🧩 Component Patterns

### Buttons

```css
/* Primary — VERTICAL gradient, SHARP CORNERS */
.btn-primary {
  background: linear-gradient(180deg, #6C2DB7 0%, #4D73D8 100%);
  color: white;
  border: none;
  border-radius: 0;  /* ← 0px — not 4px, not 8px — zero */
  padding: 12px 28px;
  font-family: var(--font-primary);
  font-weight: 500;
  letter-spacing: 0.06em;
}

/* Secondary — sharp, outline */
.btn-secondary {
  background: transparent;
  border: 1px solid var(--color-border-strong);
  border-radius: 0;
  color: var(--color-text-primary);
}

/* Arrow text link — common throughout site */
.btn-link { color: var(--color-text-primary); }
.btn-link::after { content: ' →'; }
.btn-link:hover { color: var(--color-accent-primary); }
```

### Cards

```css
.card         { background: #fff; border: 1px solid var(--color-border-default); border-radius: var(--radius-lg); }
.card-on-grey { background: #fff; box-shadow: var(--shadow-sm); border-radius: var(--radius-lg); }
```

### Navigation

```css
.nav          { background: rgba(255,255,255,0.95); border-bottom: 1px solid var(--color-border-default); }
.nav-on-photo { background: transparent; border-bottom: none; } /* over hero photo */
```

---

## 🌐 Visual Language

### Aesthetic Direction

> **Clean Editorial × Bitcoin Native — Light, Structured, Human**

- White and `#E7EBF7` grey are the dominant surfaces
- Heroes use **full-bleed photography** — real people, hands, Bitcoin in real contexts
- Violet is a **spot accent** — it appears in buttons, links, and icons only
- No gradient atmospheres, no glow effects, no dark overlays
- Typography and white space carry the visual weight

### Section Rhythm

| Section | Background |
|---------|-----------|
| Hero | Full-bleed photo/video · white text |
| What We Offer | White `#FFFFFF` |
| Why Choose Us | Light grey `#E7EBF7` |
| Partners | White |
| FAQ | Light grey |
| Contact form | White |
| Footer | Dark `#201C32` |

### Visual Motifs

| Motif | Usage |
|-------|-------|
| ₿ Bitcoin | Core — hero, icons |
| 📸 Real people / hands | Hero photography |
| ⚡ Lightning bolt | 40Node sections |
| 🔄 Exchange arrows | 40Swap sections |

---

## 🔖 Logo Usage

| Version | File | Use on |
|---------|------|--------|
| **Full Color** | `40Acres_Logo.svg` | White/grey bg — **default** |
| **Inversed (White)** | `40Acres_Inversed_Logo.svg` | Photo bg, dark footer |
| **Icon Only** | `40Acres_Icon.svg` | Favicon, small sizes |
| **40Node** | `40Node_Logo.svg` | 40Node product pages |
| **40Swap** | `40Swap_logo.svg` | 40Swap product pages |

- ✅ The `[4A]` bracket is **violet** on light, **white** on dark/photo
- ❌ Never gradient-fill any logo

---

## 🗺️ Page Anatomy

```
┌─────────────────────────────────────────────┐
│  NAV  (white or transparent over photo)      │
│  Full color logo · links · Become a Client   │
├─────────────────────────────────────────────┤
│  HERO  ← Full-bleed photo or video           │
│  White heading — plain, no gradient          │
│  White subtitle                              │
│  One gradient button (0px radius)            │
├─────────────────────────────────────────────┤
│  WHAT WE OFFER  — White bg                   │
│  Service items with → arrow links            │
├─────────────────────────────────────────────┤
│  WHY CHOOSE US  — #E7EBF7 grey bg            │
│  3 pillars — no border cards                 │
├─────────────────────────────────────────────┤
│  PARTNERS  — White bg · logo strip           │
├─────────────────────────────────────────────┤
│  FAQ  — #E7EBF7 grey bg · accordion          │
├─────────────────────────────────────────────┤
│  CONTACT FORM  — White bg                    │
│  Gradient submit button (0px radius)         │
├─────────────────────────────────────────────┤
│  FOOTER  — #201C32 dark bg                   │
│  Inversed logo · links · licenses · legal    │
└─────────────────────────────────────────────┘
```

---

## ✅ Do's and Don'ts for AI

### ✅ DO

- Treat this as a **light-mode brand** — white backgrounds by default
- Use **full-bleed photography** for heroes — white heading text, no gradient fill
- Apply gradient **only to primary CTA buttons**, direction `180deg`, `border-radius: 0`
- Use `#342E51` for all headings and body on white/grey sections
- Use `→` arrow links for navigation and service items (matches site pattern)
- Alternate sections: white → grey → white → grey

### ❌ DON'T

- Apply gradient to hero text, headings, or any typographic element
- Use gradient as a background, overlay, or decorative accent
- Round CTA button corners — primary buttons are **0px border-radius**
- Make the site dark-mode except the footer
- Add neon glow or atmospheric purple effects — wrong brand entirely
- Use gradient more than once per screen view

---

## 💬 Key Copy & Messaging

| Context | Approved Copy |
|---------|---------------|
| Hero Headline | `"Financial Freedom with Bitcoin"` |
| Hero Subtitle | `"OTC, Swaps, and Enterprise-Grade Solutions"` |
| Services Hero | `"Unlocking Global Potential with Secure Crypto Solutions"` |
| CTA | `"Get in touch →"` · `"Become a Client"` |
| 40Swap | `"Our gateway to seamless bitcoin swap — fast, secure, and simple."` |
| 40Node | `"Dedicated to enhancing the Bitcoin ecosystem through our reliable LN Node."` |
| UK Restriction | `"40 Acres does not provide services to clients in the United Kingdom (UK)."` |
| Legal | `"40 Acres, S.A. de C.V. · Registration No. 2024113630 · DASP-0046 · El Salvador"` |

---

## 🛠️ Tech Stack

| Layer | Preferred |
|-------|-----------|
| **Framework** | React (TypeScript) + Next.js |
| **Styling** | Tailwind CSS or CSS Modules |
| **Animation** | Framer Motion |
| **Font** | Degular (self-hosted) · Fallback: DM Sans |
| **Mono** | JetBrains Mono (code/addresses only) |

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=6C2DB7,4D73D8&height=100&section=footer&reversal=true" width="100%"/>

**40Acres Design System** — Covers 40Acres · 40Node · 40Swap
*Source: [40acres.pro](https://www.40acres.pro) + Brand Identity PDF + SVG Logos*

</div>
