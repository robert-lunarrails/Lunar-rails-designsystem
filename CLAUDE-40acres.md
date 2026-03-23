# ⬛ 40Acres — Design System & AI Context Guide
> Use this file as AI context when building any 40Acres, 40Node, or 40Swap product, page, or UI component.
> Drop as `CLAUDE.md` in your project root — automatically read by Claude Code, Cursor, and most AI coding tools.

---

## 1. Brand Architecture

### Parent Brand
| Field | Value |
|---|---|
| **Brand Name** | 40Acres |
| **Legal Entity** | 40 Acres, S.A. de C.V. — El Salvador |
| **Registration** | Company No. 2024113630 |
| **BTC License** | Código: 664bd64379e50005ac479693 |
| **DASP License** | PSAD-0046 |
| **Tagline** | "Financial Freedom with Bitcoin" |
| **Category** | Bitcoin Financial Services — OTC, Swaps, Enterprise Node Management |
| **Location** | El Salvador (Bitcoin-native legal tender jurisdiction) |
| **Website** | 40acres.pro |

### Child Brands (Products)
| Brand | Purpose |
|---|---|
| **40Node** | Enterprise-grade Lightning Network Node infrastructure |
| **40Swap** | Bitcoin swap gateway — fast, secure, simple BTC swaps |

### Brand Personality
Revolutionary · Bold · Visionary · Transparent

### Tone of Voice
- Write with **revolutionary conviction** — Bitcoin is financial freedom
- **Human-first** — Freedom, Empathy, Revolution, Real Human are on-brand words
- **Direct and bold** — declarative, no hedging, no empty buzzwords
- **Transparent** about licensing, regulatory status, and limitations
- Reference **El Salvador's Bitcoin legal tender** status with pride

---

## 2. Core Design Philosophy

**40Acres is a light-mode, editorial brand.** The site is primarily white and light grey. Hero sections use **full-bleed photography or video** — not dark backgrounds, not gradient washes. The violet/blue gradient is a deliberate accent used **only on CTA buttons**. It is not a decorative or atmospheric element.

### Gradient usage — exactly where it belongs
- ✅ **Primary CTA buttons** — vertical direction (top violet → bottom blue), **0px border-radius**
- ✅ **Submit buttons** in forms

### Gradient does NOT appear on
- ❌ Headings or hero text
- ❌ Section backgrounds
- ❌ Decorative dividers or overlays
- ❌ Cards, icons, borders, or underlines

---

## 3. Color System

```css
:root {
  /* --- Primitives (reference only) --- */
  --primitive-violet:    #6C2DB7;
  --primitive-blue:      #4D73D8;
  --primitive-logo-black:#342E51;
  --primitive-black:     #201C32;
  --primitive-grey:      #E7EBF7;

  /* --- Background Tokens --- */
  --color-bg-page:       #FFFFFF;   /* Default — white */
  --color-bg-section:    #E7EBF7;   /* Alternating light grey sections */
  --color-bg-dark:       #201C32;   /* Footer and dark CTA bands only */
  --color-bg-elevated:   #342E51;   /* Logo Black — inside dark areas */

  /* --- Text Tokens --- */
  --color-text-primary:  #342E51;   /* Logo Black — headings + body on light bg */
  --color-text-secondary:#5A5070;   /* Body secondary on light */
  --color-text-muted:    #8C85A6;   /* Labels, captions on light */
  --color-text-on-dark:  #FFFFFF;   /* Inside dark sections */
  --color-text-on-photo: #FFFFFF;   /* Overlaid on hero photography */

  /* --- Accent Tokens --- */
  --color-accent-primary:#6C2DB7;   /* Violet — links, icons, active states */
  --color-accent-blue:   #4D73D8;   /* Blue — gradient endpoint only */

  /* --- Gradient (buttons only) --- */
  --gradient-btn: linear-gradient(180deg, #6C2DB7 0%, #4D73D8 100%);
  /* Direction: VERTICAL (top = violet, bottom = blue) */

  /* --- Border Tokens --- */
  --color-border-default: rgba(52, 46, 81, 0.15);
  --color-border-strong:  rgba(52, 46, 81, 0.35);
  --color-border-accent:  rgba(108, 45, 183, 0.35);

  /* --- Semantic States --- */
  --color-success: #22C55E;
  --color-warning: #F59E0B;
  --color-error:   #EF4444;
}
```

### Usage Rules
| | Rule |
|---|---|
| ✅ | Default background is white — this is a **light-mode** brand |
| ✅ | Sections alternate between white and `#E7EBF7` grey |
| ✅ | `--gradient-btn` is for **buttons only**, vertical direction, 0px border-radius |
| ✅ | Headings/body on light: always `#342E51` — never gradient-filled |
| ✅ | Text on photography: white — let the photo do the visual work |
| ❌ | Never use gradient on text, backgrounds, or decorative elements |
| ❌ | Dark background only in footer and specific CTA bands |

---

## 4. Typography

### Font Stack

```css
/* Degular — sole brand typeface (commercial, self-host in production) */
@font-face { font-family:'Degular'; src:url('/fonts/Degular-Bold.woff2') format('woff2'); font-weight:700; }
@font-face { font-family:'Degular'; src:url('/fonts/Degular-Medium.woff2') format('woff2'); font-weight:500; }
@font-face { font-family:'Degular'; src:url('/fonts/Degular-Light.woff2') format('woff2'); font-weight:300; }

:root {
  --font-primary: 'Degular', 'DM Sans', system-ui, sans-serif;
  --font-mono:    'JetBrains Mono', 'Fira Code', monospace;
}
```

> **AI Agent Note:** Degular is not on Google Fonts. Use `DM Sans` as fallback — flag for production replacement.

### Type Scale

```css
:root {
  --text-hero:   clamp(48px, 8vw, 96px);
  --text-h1:     clamp(36px, 5vw, 64px);
  --text-h2:     clamp(26px, 3.5vw, 44px);
  --text-h3:     clamp(20px, 2.5vw, 32px);
  --text-h4:     clamp(16px, 2vw, 22px);
  --text-lg:     20px;
  --text-base:   16px;
  --text-sm:     14px;
  --text-xs:     12px;

  --weight-light:300; --weight-regular:400; --weight-medium:500;
  --weight-semibold:600; --weight-bold:700;

  --leading-tight:1.1; --leading-snug:1.25;
  --leading-normal:1.55; --leading-relaxed:1.75;

  --tracking-wide:0.06em; --tracking-tight:-0.02em;
}
```

### Typography by Context
| Element | Spec |
|---------|------|
| **Hero heading (on photo)** | Degular Bold · white · plain — no gradient |
| **H1–H2 on white/grey** | Degular Bold · `#342E51` |
| **H3–H4** | Degular Bold or Medium · `#342E51` |
| **Body** | Degular Light or Regular · `--color-text-secondary` |
| **Labels** | Degular Medium · uppercase · `--tracking-wide` |
| **Code/addresses** | JetBrains Mono only |

---

## 5. Spacing & Layout

```css
:root {
  --space-1:4px; --space-2:8px; --space-3:12px; --space-4:16px;
  --space-5:20px; --space-6:24px; --space-8:32px; --space-10:40px;
  --space-12:48px; --space-16:64px; --space-20:80px; --space-24:96px;

  --max-width-content:  1280px;
  --page-padding-x:     clamp(24px, 5vw, 80px);
  --section-padding-y:  clamp(64px, 10vw, 120px);

  --radius-sm:    4px;
  --radius-md:    8px;
  --radius-lg:    12px;
  --radius-xl:    16px;
  --radius-2xl:   24px;
  --radius-full:  9999px;

  --shadow-sm:  0 1px 4px rgba(52,46,81,.10);
  --shadow-md:  0 4px 16px rgba(52,46,81,.12);
  --shadow-lg:  0 8px 32px rgba(52,46,81,.14);
}
```

---

## 6. Component Patterns

### Buttons

```css
/* Base */
.btn {
  font-family: var(--font-primary);
  font-weight: var(--weight-medium);
  font-size: var(--text-sm);
  letter-spacing: var(--tracking-wide);
  padding: 12px 28px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: opacity 200ms ease, transform 200ms ease;
}

/* Primary — vertical gradient, SHARP CORNERS (0px radius) */
.btn-primary {
  background: var(--gradient-btn); /* 180deg: #6C2DB7 → #4D73D8 */
  color: #FFFFFF;
  border: none;
  border-radius: 0;  /* ← critical brand detail */
}
.btn-primary:hover { opacity: 0.88; transform: translateY(-1px); }

/* Secondary — outline, also sharp */
.btn-secondary {
  background: transparent;
  color: var(--color-text-primary);
  border: 1px solid var(--color-border-strong);
  border-radius: 0;
}
.btn-secondary:hover { border-color: var(--color-accent-primary); color: var(--color-accent-primary); }

/* Arrow link — body text with → */
.btn-link {
  background: none; border: none; padding: 0;
  color: var(--color-text-primary);
  font-family: var(--font-primary); font-weight: var(--weight-medium);
  font-size: var(--text-sm);
  display: inline-flex; align-items: center; gap: 6px;
  text-decoration: none; cursor: pointer;
}
.btn-link::after { content: '→'; transition: transform 150ms ease; }
.btn-link:hover { color: var(--color-accent-primary); }
.btn-link:hover::after { transform: translateX(4px); }
```

### Cards (on white or grey sections)

```css
/* On white section */
.card {
  background: var(--color-bg-page);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-lg);
  padding: var(--space-8);
  transition: box-shadow 250ms ease;
}
.card:hover { box-shadow: var(--shadow-md); }

/* On grey section — white card lifts off grey bg */
.card-on-grey {
  background: var(--color-bg-page);
  border-radius: var(--radius-lg);
  padding: var(--space-8);
  box-shadow: var(--shadow-sm);
}
```

### Navigation

```css
/* Default: light nav */
.nav {
  background: rgba(255,255,255,0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--color-border-default);
  padding: var(--space-4) var(--page-padding-x);
  position: sticky; top: 0; z-index: 100;
}

/* Transparent: over photography hero */
.nav-over-photo { background: transparent; border-bottom: none; }
```

### Service Item Pattern

```css
.service-item {
  padding: var(--space-8) 0;
  border-bottom: 1px solid var(--color-border-default);
}
.service-item-title {
  font-size: var(--text-h4); font-weight: var(--weight-bold);
  color: var(--color-text-primary); margin-bottom: var(--space-2);
}
.service-item-desc {
  font-size: var(--text-base); color: var(--color-text-secondary);
  line-height: var(--leading-relaxed); margin-bottom: var(--space-4);
}
```

---

## 7. Motion

```css
:root {
  --ease-spring: cubic-bezier(0.16, 1, 0.3, 1);
  --dur-fast: 150ms; --dur-base: 250ms; --dur-slow: 400ms;
}
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(18px); }
  to   { opacity: 1; transform: translateY(0); }
}
```
- Simple `fadeUp` on scroll reveal — no theatrical animations
- Button hover: opacity 88% + 1px Y lift
- No glow effects — clean editorial brand

---

## 8. Visual Language

**Clean Editorial × Bitcoin Native — Light, Structured, Human**

- White and `#E7EBF7` grey dominate all pages
- **Hero = full-bleed photography or video** — real people, Bitcoin, hands, real-world contexts
- Violet appears as a **spot color** — buttons, links, active states, icons only
- No gradient washes, no neon, no atmospheric effects
- Typography and white space carry the visual weight

### Page rhythm (alternating sections)
```
Hero          → Full-bleed photo, white text
What We Offer → White bg
Why Choose Us → Light grey (#E7EBF7) bg
Partners      → White bg
FAQ           → Light grey bg
Contact       → White bg
Footer        → Dark (#201C32)
```

---

## 9. Logo Usage

| Version | File | Use on |
|---|---|---|
| **Full Color** | `40Acres_Logo.svg` | White / light grey — default |
| **Inversed (White)** | `40Acres_Inversed_Logo.svg` | Photo bg, dark footer |
| **Icon Only** | `40Acres_Icon.svg` | Favicon, small contexts |
| **40Node** | `40Node_Logo.svg` | 40Node product contexts |
| **40Swap** | `40Swap_logo.svg` | 40Swap product contexts |

- ✅ Full Color is the default — most of the site uses it
- ✅ White logo when overlaid on photography or in the dark footer
- ❌ Never apply gradient to any logo version

---

## 10. Do's and Don'ts for AI

### ✅ DO
- Treat this as a **light-mode, white-background brand**
- Use **full-bleed photography** for heroes — white heading text on top, no gradient overlay
- Put the gradient **only on CTA buttons**, vertical (180deg), **border-radius: 0**
- Use `#342E51` for all headings on white/grey sections
- Use `→` arrow links for navigation and service list items
- Keep it clean and editorial — whitespace and type carry the weight
- Alternate sections: white → grey → white → grey

### ❌ DON'T
- Gradient on any text, heading, or hero title
- Gradient as section background, overlay, or decoration
- Round CTA button corners — primary buttons are **sharp (0px radius)**
- Make the page dark-mode except footer
- Add neon glow or atmospheric effects — wrong brand entirely
- Use the gradient more than once per screen view

---

## 11. Key Copy & Messaging

| Context | Approved Copy |
|---------|---------------|
| Hero headline | `"Financial Freedom with Bitcoin"` |
| Hero subtitle | `"OTC, Swaps, and Enterprise-Grade Solutions"` |
| Services hero | `"Unlocking Global Potential with Secure Crypto Solutions"` |
| CTA | `"Get in touch →"` · `"Become a Client"` |
| 40Swap | `"Our gateway to seamless bitcoin swap — fast, secure, and simple."` |
| 40Node | `"Dedicated to enhancing the Bitcoin ecosystem through our reliable LN Node."` |
| Enterprise | `"Simplifies liquidity management for enterprises with an intuitive, open-source solution."` |
| UK Restriction | `"40 Acres does not provide services to clients in the United Kingdom (UK)."` |
| Legal | `"40 Acres, S.A. de C.V. · Registration No. 2024113630 · DASP-0046 · El Salvador"` |

---

## 12. Tech Stack

- **React** (TypeScript) + **Next.js**
- **Tailwind CSS** or **CSS Modules**
- **Framer Motion** for scroll reveals
- **Font**: Degular (self-hosted) · Fallback: DM Sans

*Last updated: 40acres.pro + services page + Brand Identity PDF + SVG logos*
*Covers: 40Acres · 40Node · 40Swap*
