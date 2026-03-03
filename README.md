# Lumina — Landing Page

> *The Intelligence Layer for Visionary Teams*

A dark luxury single-page marketing site for **Lumina v2** — a fictional AI knowledge and collaboration platform. Single self-contained `index.html`. No build step, no frameworks, no dependencies beyond Google Fonts.

---

## Quick Start

```bash
# Open directly in any browser
open index.html

# Or serve locally
python3 -m http.server 8080
npx serve .
```

---

## File Structure

```
index.html        ← Complete page (HTML + CSS + JS, ~700 lines)
README.md         ← This file
Lumina_Report.html ← Full design & content report (printable)
```

---

## Page Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | **Navigation** | Fixed bar. Logo mark, 4 nav links, Sign In, Begin Free CTA. Glazes dark on scroll. |
| 2 | **Hero** | Full-viewport. Headline, subtext, dual CTAs, trust strip (5 logos), scroll indicator. |
| 3 | **Stats Bar** | 4 animated counters — 340K+ Teams · 98.9% Uptime · 12ms Latency · 4.9★ |
| 4 | **Features** | 6-card grid. Card 01 full-width with live node-graph. Cards 02–06 in 3-col. |
| 5 | **Platform Spotlight** | Animated orbital system (3 rings + breathing core) + 3 philosophy items. |
| 6 | **Pricing** | 3 tiers: Ember · Luminary · Sovereign. Monthly/annual toggle. Featured card elevated. |
| 7 | **Testimonials** | Dual infinite-scroll marquee rows (opposing directions). 10 personas. Hover to pause. |
| 8 | **CTA** | Email capture with focus-glow state + rating · SOC 2 · no-CC trust strip. |
| 9 | **Footer** | 4-column: Brand + social · Product · Developers · Company · Legal. |

---

## Design Tokens

All values defined as CSS custom properties on `:root`.

```css
--gold:       #c9a84c;    /* Primary accent */
--gold-light: #e8c97a;    /* Headlines, hover, logo */
--gold-dim:   #6b5526;    /* Subdued lines, secondary */
--bg:         #060606;    /* Base background */
--bg2:        #0c0c0c;    /* Section alternate */
--bg3:        #131313;    /* Card hover surface */
--text:       #ede8df;    /* Primary — warm white */
--text-mid:   #9e9890;    /* Secondary — descriptions */
--text-dim:   #52504c;    /* Tertiary — labels, metadata */
--border:     rgba(201,168,76,.12);   /* Structural borders */
--border-hi:  rgba(201,168,76,.28);  /* Active/hover borders */
--gold-glow:  rgba(201,168,76,.18);  /* Ambient glow */
```

**Typefaces** (Google Fonts):

| Family | Category | Used for |
|--------|----------|----------|
| Cormorant Garamond | Serif | Headlines, section titles, pricing numbers, logo |
| Outfit | Sans-serif | Body copy, nav links, buttons, descriptions |
| DM Mono | Monospace | Section tags, stat labels, eyebrows, footer headers |

---

## Animations

| Element | Method | Duration | Trigger |
|---------|--------|----------|---------|
| Custom cursor | JS — rAF lerp @ 0.11 | Continuous | Always on |
| Hero orbs | CSS `orbDrift` | 18–24s ease | Infinite |
| Hero content | CSS `fadeUp` staggered | 0.3–1.5s | Page load |
| Scroll indicator | CSS `scrollPulse` | 2.2s ease | Infinite |
| Stat counters | JS — `setInterval` | 1600ms | Viewport enter (40%) |
| Feature cards | CSS + IntersectionObserver | 0.55s staggered | Viewport enter (8%) |
| Node graph | CSS `nodePulse` | 3s | Infinite |
| Orbital rings | CSS `visRotate` | 18/28/38s linear | Infinite |
| Orbital core | CSS `coreBreath` | 4s ease | Infinite |
| Testimonial marquee | CSS `marquee` | 42s fwd / 52s rev | Infinite, pauses on hover |
| Pricing toggle | JS — click handler | Instant | User click |
| CTA form focus | CSS `:focus-within` | 0.3s | Input focus |
| Button shimmer | CSS `::after` sweep | 0.5s | Hover |

---

## JavaScript

Three self-contained script blocks at the bottom of `<body>`. No frameworks, no imports.

```
1. Custom cursor    — spring-lag ring interpolation via requestAnimationFrame
2. Navigation       — adds .scrolled class at 60px scroll depth
3. Feature cards    — IntersectionObserver reveal at 8% threshold
4. Stat counters    — count-up animation triggered at 40% viewport entry
5. Pricing toggle   — swaps data-monthly / data-annual on .price-num elements
```

**Total JS: ~40 lines.**

---

## Responsive Breakpoints

```css
@media (max-width: 1100px) { /* Tablet / small laptop */ }
@media (max-width: 640px)  { /* Mobile */ }
```

| Breakpoint | Key Changes |
|------------|-------------|
| ≤ 1100px | Nav links hidden · Features 3→2 col · Hero feature 1-col · Pricing stacks · Footer 2-col |
| ≤ 640px | Features 1-col · Stats 2×2 · Hero actions full-width stack · Footer 1-col |

---

## Brand Voice

**Register:** Dark luxury — deliberate, editorial, unhurried.

| Rule | Application |
|------|-------------|
| "Crafted", never "engineered" | Features header: *"Crafted for extraordinary thinking"* |
| Commands, not invitations | All headlines are declarative |
| Single action verb: **Begin** | Begin Free · Begin Luminary · Begin Free → |
| No real brand names in trust strip | Fictional enterprise names: Meridian, Archform, Vantage, Crestline, Solace |
| "Teams" not "builders" | Premium audience language throughout |

---

## Pricing Tiers

| Tier | Price | Persona |
|------|-------|---------|
| **Ember** | Free | Solo thinkers who refuse to work at a fraction of their potential |
| **Luminary** | $49/seat/mo · $39 annual | Serious teams where thinking quality determines outcomes |
| **Sovereign** | Custom | Organisations where the stakes are too high to leave thinking to chance |

---

## Known Limitations

| Item | Priority |
|------|----------|
| No product screenshot or UI proof | High |
| Trust strip uses fictional names | High |
| Missing Open Graph / Twitter Card / JSON-LD | Medium |
| No `prefers-reduced-motion` support | Medium |
| Missing keyboard focus ring styles | Medium |
| No mobile navigation drawer | Low |
| Scroll-reveal only on feature cards | Low |

---

## Browser Support

Chrome 90+ · Firefox 90+ · Safari 15+ · Edge 90+

**CSS features:** Custom properties · Grid · `mask-image` · `backdrop-filter` · `@keyframes`  
**JS features:** `IntersectionObserver` · `requestAnimationFrame` · `dataset`

---

*Design prototype — all company names, personas, and statistics are fictional.*
