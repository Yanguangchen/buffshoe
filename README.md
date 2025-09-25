## BUFF — Shoe Shine and Cleaning (Static Site)

A lightweight static website built with semantic HTML, modern CSS, and a touch of vanilla JS. The design favors a stark, editorial look with sharp edges and minimal shadows. Mobile uses a hamburger menu; dark mode is supported via a toggle.

## Tech stack
- **HTML**: static pages, no framework
- **CSS**: custom, variable-driven; responsive with media queries
- **JS**: small inline scripts for theme toggle and mobile menu
- **3D**: optional Spline embed via `@splinetool/viewer`

## Project structure
- `index.html`: home (hero, gallery, contact, Spline embed)
- `classic-shine.html`, `deep-clean.html`, `sneaker-cleaning.html`, `sole-edge-recolor.html`, `pickup-delivery.html`
- `styles.css`: global styles, themes, components, responsive rules
- `assets/`: images

## Run locally
Open `index.html` directly in a browser, or serve the folder:

```bash
npx serve .
# or any static server
```

## CSS design system

### Color palette (CSS variables)
- `--page`: light background `#f7f5ef`; dark uses gradients
- `--card`: `#ffffff` (light), `#151517` (dark)
- `--text`: `#111827` (light), `#ffffff` (dark)
- `--muted`: `#4b5563` (light), `#c7c7c7` (dark)
- `--ring`: focus/border tint (light rgba black 12%, dark rgba white 8%)
- `--input-bg` / `--input-text` / `--placeholder`: form colors
- Accent: `--emerald` `#10b981`, `--emeraldHover` `#0ea371`
- `--translucent-surface`: low-opacity surface tint per theme

Dark theme is activated by setting `data-theme="dark"` on `<html>` and is persisted in `localStorage` by the theme toggle.

### Layout and spacing
- Container width: `max-width: 1100px`, horizontal padding `24px`
- Sections account for fixed nav via `scroll-margin-top: 180px`

### Typography
- Hero title (`.hero h1`): large, stark headline (desktop ~56px) with no text-shadow
- Body text uses system UI stack

### Components
- **Navbar** (`.nav-wrap .nav`): pill-style on desktop; on mobile it collapses to a **hamburger** button
- **Mobile menu** (`.mobile-menu`): fixed overlay panel; animated fade/scale with `.open` class; controlled by hamburger JS
- **Dropdowns** (`.dropdown`): appear on hover/focus on desktop; glassy treatment matching nav
- **Gallery** (`.gallery .thumb`): sharp edges, no shadow or hover zoom; responsive columns at 640px and 900px
- **Buttons** (`.btn`): emerald pill; alternate `.btn.alt` available
- **FAB** (`.fab a`): WhatsApp CTA bottom-right; on mobile shows icon and text with compact padding
- **Contact** (`.contact`): stark block; square corners, no shadow or glass effect
- **Spline** (`.spline-container`): constrained to `50vh` height with `margin-top: 10%`

### Responsiveness
- Breakpoints used:
  - `@media (max-width: 640px)`: mobile
  - `@media (min-width: 641px) and (max-width: 1024px)`: tablet
- Hero top margins (home): desktop 10%, tablet 20%, mobile 30%
- Mobile navbar: smaller padding/gaps; hamburger shows, primary nav items hidden

## Behavior (JS)
- Theme toggle updates `data-theme` and persists preference
- Hamburger toggles `.mobile-menu.open`, updates ARIA `aria-expanded`, and closes on outside click

## Spline embed
Included on the homepage via:
```html
<script type="module" src="https://unpkg.com/@splinetool/viewer@1.10.70/build/spline-viewer.js"></script>
<div class="spline-container">
  <spline-viewer url=".../scene.splinecode"></spline-viewer>
</div>
```
Adjust container height or margins in `styles.css` (`.spline-container`).

## Branding
- Page titles and navbar labeling can be updated to the final brand name: **BUFF**
- Favicon/OG images: replace `icon.png` and add meta tags as needed

## Accessibility
- Buttons and links include accessible labels
- Mobile menu button manages `aria-expanded`
- Follow-ups: refine dropdown ARIA roles for stricter validators

## Deployment
- Any static host works (GitHub Pages, Netlify, Vercel). For private repos, use a deploy token or connect provider to the repo.

## License
Proprietary — © BUFF. All rights reserved.


