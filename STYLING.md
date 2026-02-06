# WeSpeakToRobots.ai - Styling Reference

Quick reference for reusing this design system across the brand.

## Colour Palette

| Token | Hex | Usage |
|---|---|---|
| `--primary` | `#50FA9E` | Green - main accent, CTAs, highlights, glows |
| `--primary-fg` | `#000000` | Text on primary buttons |
| `--secondary` | `#2557D6` | Blue - secondary accent, icons, interstitials |
| `--secondary-fg` | `#FFFFFF` | Text on secondary elements |
| `--background` | `#000000` | Page background |
| `--foreground` | `#FFFFFF` | Main text colour |
| `--surfacedark` | `#1F1F1F` | Card/section backgrounds, borders |
| `--brandaccent` | `#FFC09F` | Peach/salmon - tertiary accent |

### Glow / Shadow Values
- Green glow (buttons): `box-shadow: 0 0 30px rgba(80, 250, 158, 0.5)`
- Green glow (badges): `box-shadow: 0 0 20px rgba(80, 250, 158, 0.4)`
- Blue glow (buttons): `box-shadow: 0 0 30px rgba(37, 87, 214, 0.5)`
- Subtle borders: `border: 1px solid rgba(255, 255, 255, 0.05)`
- Hover borders: `rgba(80, 250, 158, 0.5)` or `rgba(37, 87, 214, 0.5)`

## Typography

**Font:** Rubik (Google Fonts) - used for everything.

| Element | Weight | Size (desktop) | Notes |
|---|---|---|---|
| Hero title | 900 (Black) | `9rem` / `15vw` mobile | Uppercase, `line-height: 0.85`, `letter-spacing: -0.05em` |
| Section titles | 900 (Black) | `4.5rem` | Key word highlighted in `--primary` green |
| XL section titles | 900 (Black) | `5rem` | Used in services split layout |
| Card titles | 700 (Bold) | `1.25rem` - `2rem` | |
| Body text | 300 (Light) | `1rem` - `1.125rem` | `color: rgba(255, 255, 255, 0.5-0.6)` |
| Subtitles | 300 (Light) | `1.25rem` - `1.5rem` | `letter-spacing: 0.05em` |
| Labels | 600 (Semibold) | `0.875rem` | Uppercase, `letter-spacing: 0.2em`, primary green |
| Nav links | 500 (Medium) | `0.875rem` | Uppercase, `letter-spacing: 0.05em` |

## Layout

- **Max width:** `1920px` (`max-w: 120rem`)
- **Padding:** `1.5rem` mobile, `3rem` desktop
- **Border radius:** Very generous throughout:
  - Buttons: `9999px` (full pill)
  - Cards: `2rem` - `2.5rem`
  - CTA sections: `3rem`
  - Icon boxes: `0.75rem` - `1.25rem`

## Buttons

All buttons use `border-radius: 9999px` (pill shape).

| Style | Class | Look |
|---|---|---|
| Solid | `btn btn-lg btn-solid` | White bg, black text. Hover: green bg + glow |
| Primary | `btn btn-lg btn-primary` | Green bg, black text. Hover: glow + lift |
| Outline | `btn btn-lg btn-outline` | Transparent, white border. Hover: green border/text |
| Secondary | `btn btn-lg btn-secondary-solid` | Blue bg, white text. Hover: glow + lift |

Sizes: `btn-lg` = 4rem height, `btn-xl` = 5rem height.

## Cards

Dark surface cards with subtle borders:

```css
background: #1F1F1F;
border-radius: 2rem;
padding: 2rem - 2.5rem;
border: 1px solid rgba(255, 255, 255, 0.05);
/* Hover: */
border-color: rgba(80, 250, 158, 0.5);
transform: translateY(-4px);
```

Icon boxes inside cards: `3.5rem` - `4rem` square, `border-radius: 1rem`, coloured background matching accent.

## Animations

### Floating Items (Hero)
All items bob vertically in sync:
```css
animation: float-name 4s ease-in-out infinite;

@keyframes float-name {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-40px); }
}
```
Applied via JS (`requestAnimationFrame`) after Lucide icons have loaded to prevent reflow killing the animation.

### Floating Item Positions
| Item | Position | Notes |
|---|---|---|
| AI Native badge | `top: 15%; left: 20%` | Green pill, solid bg |
| Mouse pointer | `top: 27%; right: 12%` | Blue, `3.25rem`, rotated -15deg |
| Bot icon box | `bottom: 25%; left: 12%` | Frosted glass box, rotated 12deg |
| Est. 2024 badge | `bottom: 15%; right: 12%` | Green outline pill |

### Hero Background
Three concentric rotating circles:
- Sizes: `35vw`, `70vw`, `105vw`
- `border: 1px solid rgba(80, 250, 158, 0.15)`, `opacity: 0.2`
- Alternate clockwise/counter-clockwise, 20-30s duration

### Scroll Reveals
Elements with class `reveal` fade up on scroll via IntersectionObserver:
```css
.reveal { opacity: 0; transform: translateY(30px); transition: 0.6s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }
```
Stagger children with `.stagger > *` and `style="--i: N"`.

### Marquee Ticker
Horizontal scroll, 7 words doubled for seamless loop:
- Words: SECURITY, COMPLIANCE, OPTIMIZATION, STRATEGY, INTELLIGENCE, AUDITING, FUTURE
- Stroke text: `-webkit-text-stroke: 1px rgba(255, 255, 255, 0.3); color: transparent`
- Hover: stroke removed, fills green
- `animation: marquee-scroll 20s linear infinite`

### Film Grain
Fixed SVG noise overlay, `opacity: 0.03`, `mix-blend-mode: overlay`.

### Logo Scan Effect
The logo image uses a CSS mask animation that sweeps a light band vertically:
```css
.scan-anim {
  mask-image: linear-gradient(to bottom, transparent 0%, white 50%, transparent 100%);
  mask-size: 100% 200%;
  animation: scanMask 2s linear infinite;
}
```

## Icons

All icons from [Lucide](https://lucide.dev/), loaded via CDN.

Key icons used:
- `mouse-pointer-2` - Hero floating item
- `bot` - Hero floating item
- `zap` - Marquee separators, Rapid Implementation
- `brain` - Deep Expertise
- `shield` - Auditing
- `trending-up` - Measurable Results
- `users` - Collaborative Approach, Training
- `award` - Industry Recognition
- `terminal` - System Ready interstitial
- `globe` - Strategy Consulting
- `cpu` - Implementation
- `arrow-right` - CTA buttons
- `target` - Mission
- `lightbulb` - Vision
- `mail`, `phone`, `map-pin` - Contact info
- `send` - Contact form submit
- `menu`, `x` - Mobile nav toggle

## Page Structure

All pages share: header (fixed, `5rem` height) + footer (4-column grid) + grain overlay.

| Page | Key Sections |
|---|---|
| Home | Hero with floaters > Marquee > Advantage (6 cards) > Parallax "SYSTEM READY" > Services split (4 cards) > CTA |
| Services | Page header > 2-col grid (4 detailed cards) > CTA banner |
| About | Page header > Values (3 cards) > Our Story > CTA banner |
| Contact | Page header > 2-col (form + info/hours) |

## Contact Details

- **Display email:** jack@wespeaktorobots.ai
- **mailto:** hello@wetalktorobots.ai
- Form currently uses mailto: link - replace with backend when on 123-reg
