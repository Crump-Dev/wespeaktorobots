# WeSpeakToRobots.ai — Design System & Styling Reference

Reusable design system reference. Everything here can be lifted for other sites.

## Brand & Tone

**Brand positioning:** "We Speak To Robots" = credibility/expertise (about us). The copy leans into outcomes and benefits (about them).

**Tone:** Confident and knowledgeable but approachable and straight-talking. A senior partner who's also good company at the pub. Not stuffy, not matey.

**Copy rules:**
- Plain English, always. No jargon.
- Lead with benefits, not features.
- "You/your" more than "we/our".
- Short sentences. Direct language.

## Colour Palette

| Token | Hex | Usage |
|---|---|---|
| `--primary` | `#50FA9E` | Green — main accent, CTAs, highlights, glows |
| `--primary-fg` | `#000000` | Text on primary buttons |
| `--secondary` | `#2557D6` | Blue — secondary accent, icons, interstitials |
| `--secondary-fg` | `#FFFFFF` | Text on secondary elements |
| `--background` | `#000000` | Page background |
| `--foreground` | `#FFFFFF` | Main text colour |
| `--surfacedark` | `#1F1F1F` | Card/section backgrounds |
| `--brandaccent` | `#FFC09F` | Peach — tertiary accent |

### Background Utilities

| Class | Value |
|---|---|
| `.bg-primary` | `#50FA9E` (solid green) |
| `.bg-secondary` | `#2557D6` (solid blue) |
| `.bg-brandaccent` | `#FFC09F` (solid peach) |
| `.bg-primary-10` | `rgba(80, 250, 158, 0.1)` |
| `.bg-secondary-20` | `rgba(37, 87, 214, 0.2)` |

### Glow / Shadow Values

- Green glow (buttons): `box-shadow: 0 0 30px rgba(80, 250, 158, 0.5)`
- Green glow (badges): `box-shadow: 0 0 20px rgba(80, 250, 158, 0.4)`
- Blue glow (buttons): `box-shadow: 0 0 30px rgba(37, 87, 214, 0.5)`
- Subtle borders: `border: 1px solid rgba(255, 255, 255, 0.05)`
- Hover borders: `rgba(80, 250, 158, 0.5)` or `rgba(37, 87, 214, 0.5)`

## Typography

**Font:** Rubik (Google Fonts) — used for everything.

| Element | Weight | Size (desktop) | Notes |
|---|---|---|---|
| Hero title | 900 | `9rem` / `15vw` mobile | Uppercase, `line-height: 0.85`, `letter-spacing: -0.05em` |
| Section titles | 900 | `4.5rem` | Key word in `.green` or `.blue` span |
| XL section titles | 900 | `5rem` | Used in services split layout |
| Page header titles | 900 | `6rem` | Inner pages (services, about, etc.) |
| Card titles | 700 | `1.25rem` – `2rem` | |
| Body text | 300 | `1rem` – `1.125rem` | `color: rgba(255, 255, 255, 0.5-0.6)` |
| Subtitles | 300 | `1.25rem` – `1.5rem` | `letter-spacing: 0.05em` |
| Labels | 600 | `0.875rem` | Uppercase, `letter-spacing: 0.2em`, primary green |
| Nav links | 500 | `0.875rem` | Uppercase, `letter-spacing: 0.05em` |
| Parallax title | 900 | `6rem` | Uppercase |

## Layout

- **Max width:** `1920px`
- **Container padding:** `1.5rem` mobile, `3rem` desktop (1024px+)
- **Section padding:** `8rem` top and bottom
- **Border radius:**
  - Buttons: `9999px` (full pill)
  - Cards: `2rem` – `2.5rem`
  - CTA outer: `3rem`
  - Icon boxes: `0.75rem` – `1.25rem`

## Navigation

**7 pages:** Home | Services | Solutions | Pricing | About | Team | Contact

- Fixed header, `5rem` height, `rgba(0,0,0,0.95)` with `backdrop-filter: blur(8px)`
- Desktop nav: flex, `gap: 2.5rem`, hidden below 768px
- Mobile nav: hamburger toggle, absolute dropdown below header
- Active page: `class="active"` on desktop nav link, `color: var(--primary)`

## Buttons

All buttons are pill-shaped (`border-radius: 9999px`).

| Style | Class | Look |
|---|---|---|
| Solid | `.btn .btn-lg .btn-solid` | White bg, black text → green bg + glow on hover |
| Primary | `.btn .btn-lg .btn-primary` | Green bg, black text → glow + lift on hover |
| Outline | `.btn .btn-lg .btn-outline` | Transparent, white border → green border/text on hover |
| Secondary | `.btn .btn-lg .btn-secondary-solid` | Blue bg, white text → glow + lift on hover |

**Sizes:** `.btn-lg` = `4rem` height, `.btn-xl` = `5rem` height

## Component Patterns

### Advantage Cards (`.advantage-card`)
Used on: homepage "What You Get", pricing "Why This Works"

```
.advantage-grid  →  1col / 2col (768px) / 3col (1024px)
  .advantage-card  →  dark surface, icon-box + h3 + p
```

- Icon box: `3.5rem`, `border-radius: 1rem`
- Hover: green border, lift 4px
- Stagger with `.stagger` + `style="--i:N"`

### Value Cards (`.value-card`)
Used on: about page values, solutions delivery models

```
.values-grid  →  1col / 3col (1024px)
  .value-card  →  dark surface, icon-box + h3 + p
```

- Icon box: `4rem`, `border-radius: 1.25rem`
- Simpler variant of advantage card (no hover lift)

### Service Cards (`.service-card`)
Used on: homepage "What We Do", pricing "Three Steps"

```
.service-card  →  numbered cards with side icon
  .service-number  →  5rem, 900 weight, rgba(255,255,255,0.24)
  h3 + p
  .service-features  →  2-column grid of checkmark items
  .service-side-icon  →  8rem box, hidden on mobile
```

- Side icons use `data-lucide` at `3rem`, colour `var(--secondary)`, `opacity: 0.5`
- Cards stack vertically with `margin-top: 2rem` between

### SP Cards (`.sp-card`)
Used on: services page, solutions "What We Build"

```
.services-page-grid  →  1col / 2col (1024px)
  .sp-card  →  icon-box + h3 + p + ul.sp-features + CTA button
```

- Icon box: `4rem`, `border-radius: 1.25rem`
- Feature list: vertical stack with checkmark SVGs (`1.125rem`, green)
- CTA: `.btn .btn-lg .btn-outline` at bottom
- Hover: green border, lift 4px

### Story Section (`.story-section`)
Used on: about page "Our Story", pricing "Common Questions"

- Dark surface card (`var(--surfacedark)`, `border-radius: 2.5rem`)
- Padding: `3rem 2rem` mobile, `4rem 3rem` desktop
- Contains h2 + paragraphs
- Good for prose content and Q&A sections

### CTA Banner (`.cta-banner`)
Used on: all inner pages

- Blue background (`var(--secondary)`), `border-radius: 2rem`
- Centred: h2 + p + `.btn .btn-lg .btn-solid`
- `margin-top: 4rem`

### CTA Section (`.cta-section`)
Used on: homepage (bigger, more dramatic)

- `.cta-outer` → blue-tinted background, `border-radius: 3rem`
- `.cta-inner` → dark bg, border, `border-radius: 2.5rem`
- `.cta-dots` → animated radial-gradient dot pattern
- Centred: `.section-title` + p + `.btn .btn-xl .btn-primary`

### Page Header (`.page-header`)
Used on: all inner pages

- `padding: 10rem 0 5rem`
- h1: `3rem` mobile → `5rem` tablet → `6rem` desktop
- p: `rgba(255,255,255,0.6)`, `max-width: 700px`
- Key word in h1 uses `.green` span

### Contact Components

```
.contact-grid  →  1col / 2col (1024px)
  .contact-form-card  →  dark surface with form
  .contact-info  →  heading + items
    .contact-item  →  icon-box + text
  .hours-card  →  dark surface with time rows
```

- Form inputs: dark bg, subtle border, green focus state
- Contact form uses mailto: link (replace with backend when ready)

### Team Cards (custom `<style>` in team.html)

```
.team-grid  →  1col / 3col (1024px)
  .team-card  →  photo + info
    .team-photo  →  square aspect ratio, object-fit cover
    .team-info  →  h3 + .team-role + .team-bio + .team-link
```

- Photo fallback: `.team-photo-placeholder` with user icon
- Role colour: `var(--primary)`
- Bio: `rgba(255,255,255,0.5)`, `font-weight: 300`

## Hero Section

### Floating Items
4 positioned elements that bob vertically after Lucide icons load:

| Item | Position | Type |
|---|---|---|
| "AI Native" badge | `top:15%; left:20%` | Green solid pill |
| Mouse pointer icon | `top:27%; right:12%` | Blue icon, rotated -15deg |
| Bot icon box | `bottom:25%; left:12%` | Frosted glass box, rotated 12deg |
| "Est. 2025" badge | `bottom:15%; right:12%` | Green outline pill |

Animation: `4s ease-in-out infinite`, `translateY(-40px)` at midpoint.
Applied via JS (`requestAnimationFrame`) after Lucide has swapped the DOM.

### Background Circles
Three concentric rotating circles:
- Sizes: `35vw`, `70vw`, `105vw`
- `border: 1px solid rgba(80, 250, 158, 0.15)`, `opacity: 0.2`
- Alternate CW/CCW, 20–30s duration

### Hero Content
- Title: uppercase, `font-weight: 900`, green `.green` span with drop-shadow
- Divider: animated blue gradient line expanding from 0 to 100% width
- Subtitle: `max-width: 600px`, `letter-spacing: 0.05em`
- Buttons: 2-up, centred, flex-wrap

## Marquee Ticker

Horizontal infinite scroll, 8 words doubled for seamless loop:
- Words: `AI STRATEGY` / `MORE TIME OFF` / `AUTOMATION` / `BIGGER PROFITS` / `AUDITING` / `LESS ADMIN` / `IMPLEMENTATION` / `FEWER HEADACHES`
- Alternates capability words with outcome words
- Stroke text: `-webkit-text-stroke: 1px rgba(255,255,255,0.5); color: transparent; opacity: 0.5`
- Hover: stroke removed, fills green
- Separators: blue zap icons
- `animation: marquee-scroll 20s linear infinite`

## Parallax Interstitial

- `80vh` height, background image with `opacity: 0.4`
- Gradient overlay top and bottom
- Centred content: large icon + `.parallax-title` + `.parallax-sub`
- Title: `3rem` mobile, `6rem` desktop, uppercase

## Animations

### Scroll Reveals
```css
.reveal { opacity: 0; transform: translateY(30px); transition: 0.6s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-left { opacity: 0; transform: translateX(-30px); transition: 0.6s ease; }
```
Triggered by IntersectionObserver at 10% visibility with 50px bottom margin.

### Stagger Pattern
```css
.stagger > * { transition-delay: calc(var(--i, 0) * 0.1s); }
```
Set `style="--i:0"`, `--i:1`, etc. on child elements.

### Film Grain
Fixed SVG noise overlay: `opacity: 0.03`, `mix-blend-mode: overlay`, `z-index: 100`.

## Icons

All from [Lucide](https://lucide.dev/), loaded via CDN (`unpkg.com/lucide@latest`).

### Key Icons by Page

**Homepage:**
`mouse-pointer-2`, `bot` (hero floaters) · `clock`, `pound-sterling`, `zap`, `trending-up`, `message-circle`, `smile` (advantage cards) · `coffee` (parallax) · `globe`, `search`, `cpu`, `users` (service cards) · `zap` (marquee separators)

**Services:**
`globe` (strategy) · `cpu` (implementation) · `search` (audit) · `users` (training)

**Solutions:**
`plug`, `box`, `layers` (delivery models) · `message-square`, `file-text`, `git-branch`, `bar-chart-3` (solution types)

**Pricing:**
`coffee`, `search`, `handshake` (three steps) · `shield-check`, `target`, `trending-up`, `eye`, `scale`, `heart-handshake` (why it works)

**About:**
`target` (mission) · `lightbulb` (vision) · `users` (how we work)

**Contact:**
`mail`, `phone`, `map-pin` (info items) · `send` (form submit)

**Shared:**
`arrow-right` (CTA buttons) · `menu`, `x` (mobile nav) · `mail`, `linkedin`, `twitter` (footer social)

## Page Structure

All pages share: fixed header (`5rem`) + footer (4-column grid) + grain overlay + Lucide CDN + `main.js`.

| Page | Sections |
|---|---|
| **Home** | Hero with floaters → Marquee → Advantage (6 cards) → Parallax → Services split (4 numbered cards) → CTA section |
| **Services** | Page header → 2-col grid (4 sp-cards) → CTA banner |
| **Solutions** | Page header → 3 value cards (delivery models) → 4 sp-cards (solution types, section-dark) → CTA banner |
| **Pricing** | Page header → 3 numbered steps (900px container) → 6 advantage cards (section-dark) → Story section (FAQ) → CTA banner |
| **About** | Page header → 3 value cards → Story section → CTA banner |
| **Team** | Custom heading → 3 team cards → CTA banner |
| **Contact** | Page header → 2-col (form + info/hours) |

## Footer

4-column responsive grid (`1fr / 2fr / 1fr / 1fr / 1.5fr`):
1. **Brand** — logo + description text
2. **Quick Links** — Home, Services, Solutions, Pricing, About, Contact
3. **Services** — AI Strategy, Implementation, Business Audit, Training & Support
4. **Connect** — social icons + tagline + CTA button

Footer bottom: copyright (dynamic year) + Privacy Policy + Terms of Service

## Contact Details

- **Email:** hello@wespeaktorobots.ai
- Form currently uses mailto: link — replace with backend when ready

## Infrastructure

- **Hosting:** AWS S3 (`wespeaktorobots-site`) + CloudFront (`E3S477MNSASBSF`)
- **Domain:** `d1o6xuugeh39g9.cloudfront.net` (custom domain TBD)
- **GitHub:** `Crump-Dev/wespeaktorobots`
- **Deploy:** `aws s3 sync` + `aws cloudfront create-invalidation --distribution-id E3S477MNSASBSF --paths "/*"`
