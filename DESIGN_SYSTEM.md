# Sol-4 Investment & Solicitors — Design System v1.0

> **Brand Mantra:** *Authority without distance. Closeness without informality.*

---

## 1. Color System

### 1.1 Primary — Lila Scale

| Token | Hex | HSL | Usage |
|---|---|---|---|
| `--lila-50` | `#F5F0FA` | 270 40% 96% | Page background tint, subtle fills |
| `--lila-100` | `#E8DDEF` | 270 35% 90% | Card backgrounds, hover states |
| `--lila-200` | `#D4C0E3` | 272 35% 82% | Borders, dividers |
| `--lila-300` | `#B898D4` | 273 38% 72% | Secondary icon fills |
| `--lila-400` | `#9B6FC4` | 274 42% 60% | Interactive hover accent |
| `--lila-500` | `#7E4DB3` | 274 44% 50% | **Primary brand color** — buttons, links |
| `--lila-600` | `#6A3D9A` | 274 43% 42% | Active/pressed states |
| `--lila-700` | `#553180` | 274 44% 35% | Dark UI elements, footer bg |
| `--lila-800` | `#3E2360` | 274 46% 26% | Deep accents |
| `--lila-900` | `#271540` | 274 48% 17% | Darkest text on light bg |

### 1.2 Neutrals

| Token | Hex | Usage |
|---|---|---|
| `--neutral-900` | `#1A1A2E` | Primary body text (never pure #000) |
| `--neutral-700` | `#4A4A5A` | Secondary text, labels |
| `--neutral-500` | `#7A7A8A` | Placeholder text, disabled states |
| `--neutral-300` | `#C8C8D4` | Borders, subtle dividers |
| `--neutral-100` | `#EDEDF2` | Light separators |
| `--white-warm` | `#FAF8FC` | Base page background (lila-tinted white) |
| `--white-pure` | `#FFFFFF` | Card surfaces only |

### 1.3 Semantic / Accent

| Token | Hex | Usage |
|---|---|---|
| `--whatsapp` | `#25D366` | WhatsApp button **only** |
| `--success` | `#2ECC71` | Form success feedback |
| `--error` | `#E74C3C` | Form error feedback |
| `--warning` | `#F39C12` | Warning alerts |

> ⛔ **REGLA DE ORO — ZERO BLUE:** No shade of blue (#0000FF–#00BFFF or any blue-dominant hue 200°–250° HSL) may appear anywhere: buttons, links, shadows, gradients, icons, borders, or focus rings. Replace default browser focus outlines with `--lila-400`.

### 1.4 Background Strategy — "No Flat White"

```css
body {
  background-color: var(--white-warm);
  background-image:
    radial-gradient(ellipse at 20% 0%, rgba(126,77,179,0.04) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 100%, rgba(126,77,179,0.03) 0%, transparent 50%);
}
```

Alternate sections between `--lila-50` and `--white-warm`.

---

## 2. Typography

### 2.1 Font Stack

| Role | Family | Weight |
|---|---|---|
| Headings | **DM Sans** | 700 |
| Body | **Inter** | 400 |
| Body emphasis | **Inter** | 500 |
| UI / Buttons | **Inter** | 600 |

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

### 2.2 Type Scale

| Token | Size | Line-Height | Weight | Element |
|---|---|---|---|---|
| `--text-hero` | 56px | 1.1 | 700 | Hero H1 |
| `--text-h1` | 44px | 1.15 | 700 | Section headings |
| `--text-h2` | 32px | 1.2 | 700 | Sub-headings |
| `--text-h3` | 24px | 1.3 | 700 | Card titles |
| `--text-h4` | 20px | 1.35 | 600 | Small headings |
| `--text-body` | 17px | 1.65 | 400 | Body copy |
| `--text-body-sm` | 15px | 1.6 | 400 | Captions |
| `--text-caption` | 13px | 1.5 | 500 | Labels, tags |
| `--text-button` | 15px | 1 | 600 | Button labels |

Mobile (≤768px): Hero→36px, H1→30px, H2→24px, Body→16px.

---

## 3. Spacing (base 8px)

| Token | Value |
|---|---|
| `--space-1` | 4px |
| `--space-2` | 8px |
| `--space-3` | 12px |
| `--space-4` | 16px |
| `--space-5` | 24px |
| `--space-6` | 32px |
| `--space-7` | 48px |
| `--space-8` | 64px |
| `--space-9` | 80px |
| `--space-10` | 120px |

Container: `max-width: 1200px`, `padding: 0 24px`.
Breakpoints: 480 / 768 / 1024 / 1440px.

---

## 4. Components

### Buttons — `border-radius: 8px` always

**Primary:** `bg: --lila-500`, white text, hover→`--lila-600` + translateY(-2px) + shadow.
**Secondary:** transparent bg, `--lila-500` text, 2px `--lila-300` border, hover→`--lila-50` fill.
**WhatsApp:** `bg: #25D366`, white text. Green reserved exclusively for this.

### Cards — `border-radius: 12px`

White bg, 1px `--neutral-100` border, `--shadow-md`. Hover: translateY(-4px) + `--shadow-lg`.

### Form Inputs — `border-radius: 8px`

1.5px `--neutral-300` border. Focus: `--lila-400` border + 3px lila ring.

---

## 5. Shadows

| Token | Value |
|---|---|
| `--shadow-sm` | `0 1px 4px rgba(30,30,46,0.06)` |
| `--shadow-md` | `0 4px 16px rgba(30,30,46,0.08)` |
| `--shadow-lg` | `0 8px 30px rgba(126,77,179,0.12)` |
| `--shadow-xl` | `0 16px 48px rgba(126,77,179,0.18)` |

---

## 6. Icons

Lucide Icons — line style, 1.75px stroke, 24×24 default. Color: `--lila-500` on light, white on dark.

---

## 7. Images

- ❌ No stock photos (handshakes, keys, generic meetings)
- ✅ Mar & Vicente photos only (3:4 portrait)
- ✅ Vector illustrations, modern iconography, lila-toned abstract graphics
- Placeholders: `--lila-100` fill + Lucide icon

---

## 8. Animations

**Scroll reveal:** opacity 0→1, translateY(30px→0), 600ms ease-out via IntersectionObserver.
**Logo:** Scale(1.06) rotate(-2deg) on hover; fade-in entrance on page load.
**Carousel:** Infinite horizontal scroll 25s, logos grayscale→color on hover.
**Defaults:** color 200ms, transform 250ms, shadow 250ms, opacity 600ms.

---

## 9. CSS Variables (Master)

```css
:root {
  --lila-50:#F5F0FA; --lila-100:#E8DDEF; --lila-200:#D4C0E3;
  --lila-300:#B898D4; --lila-400:#9B6FC4; --lila-500:#7E4DB3;
  --lila-600:#6A3D9A; --lila-700:#553180; --lila-800:#3E2360;
  --lila-900:#271540;
  --neutral-900:#1A1A2E; --neutral-700:#4A4A5A; --neutral-500:#7A7A8A;
  --neutral-300:#C8C8D4; --neutral-100:#EDEDF2;
  --white-warm:#FAF8FC; --white-pure:#FFFFFF;
  --whatsapp:#25D366; --success:#2ECC71; --error:#E74C3C; --warning:#F39C12;
  --font-heading:'DM Sans','Inter',system-ui,sans-serif;
  --font-body:'Inter',system-ui,-apple-system,sans-serif;
  --space-1:4px; --space-2:8px; --space-3:12px; --space-4:16px;
  --space-5:24px; --space-6:32px; --space-7:48px; --space-8:64px;
  --space-9:80px; --space-10:120px;
  --radius-sm:6px; --radius-md:8px; --radius-lg:12px; --radius-xl:16px;
  --shadow-sm:0 1px 4px rgba(30,30,46,0.06);
  --shadow-md:0 4px 16px rgba(30,30,46,0.08);
  --shadow-lg:0 8px 30px rgba(126,77,179,0.12);
  --shadow-xl:0 16px 48px rgba(126,77,179,0.18);
}
```

---

## 10. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| `--lila-500` for primary actions | Any shade of blue anywhere |
| `--white-warm` tinted backgrounds | Flat #FFFFFF page bg |
| border-radius 8–12px | Square or pill shapes |
| Lucide line icons | Filled/emoji icons |
| Only Mar & Vicente photos | Stock photos or other team |
| Green only for WhatsApp | Green for primary buttons |
| Fade-in/slide-up reveals | Bouncy/flashy animations |
| DM Sans headings + Inter body | More than 2 font families |
| `--lila-400` focus outlines | Default blue browser focus |
