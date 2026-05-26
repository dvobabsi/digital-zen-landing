# Digital Zen — Landing Page Development Prompt

> **Role:** You are a Senior Frontend Developer and UX/UI Designer specializing in high-converting SaaS and Chrome Extension landing pages.  
> **Task:** Build a complete, production-ready landing page for the Digital Zen browser extension based on the full strategy below.

---

## Product Context

**Name:** Digital Zen  
**Type:** Browser extension (Chrome, Edge, Brave, Firefox, Vivaldi, Opera)  
**Tagline:** Block distractions. Focus deeply. Work better.  
**Description:** A productivity browser extension that blocks distracting websites on a flexible schedule and includes a fully configurable Pomodoro timer for structured work sessions.  
**Primary CTA:** Install from Chrome Web Store  
**CTA Link:** `https://chromewebstore.google.com/detail/digital-zen/nfonpieonaajbkncdoijinhplnfpkgkj`  
**GitHub:** `https://github.com/DenHelloWorld`  
**License:** MIT (Open Source)  
**Price:** Free  

**Target Audience:** Office workers, freelancers, students, programmers — anyone struggling with digital distractions and poor time structure.

---

## Tech Stack & Constraints

- Single HTML file (HTML + CSS + JS, no build tools)
- No external frameworks (vanilla JS only)
- Fonts via Google Fonts CDN
- Icons via Lucide or Phosphor Icons CDN
- Mobile-first, fully responsive
- Must work without a backend

---

## Visual Design System

### Color Palette

```css
--color-bg:         #0f0d16;   /* Deep dark background */
--color-surface:    #1a1625;   /* Card / section surface */
--color-surface-2:  rgba(255, 255, 255, 0.04); /* Glassmorphism surface */
--color-border:     rgba(124, 58, 237, 0.2);   /* Subtle violet border */
--color-primary:    #7c3aed;   /* Violet-700 — main accent */
--color-primary-lt: #a78bfa;   /* Violet-400 — light accent */
--color-primary-glow: rgba(124, 58, 237, 0.35); /* CTA glow effect */
--color-text:       #f8fafc;   /* Primary text */
--color-text-muted: #94a3b8;   /* Secondary text */
--color-text-hint:  #64748b;   /* Hint / caption text */
```

### Typography

```css
/* Display font — bold, geometric */
font-family: 'Bricolage Grotesque', sans-serif;  /* H1, H2 */

/* Body font — clean, readable */
font-family: 'DM Sans', sans-serif;              /* Body, UI */
```

| Element | Size | Weight | Line Height |
|---------|------|--------|-------------|
| H1 | 60–72px | 700 | 1.1 |
| H2 | 36–42px | 600 | 1.2 |
| H3 | 22–24px | 600 | 1.3 |
| Body | 17–18px | 400 | 1.7 |
| Caption | 13–14px | 400 | 1.5 |

### Motion & Animations

- **Scroll reveal:** `opacity: 0 → 1` + `translateY(24px → 0)` via `IntersectionObserver`, `duration: 0.5s`, staggered `delay` per element
- **CTA pulse:** Keyframe `box-shadow` pulsing with `--color-primary-glow`, `2s infinite`
- **Hero progress ring:** SVG `stroke-dashoffset` animated from 0 to 65% (simulating an active session), `3s ease-in-out`
- **Hero breathing effect:** Subtle `scale(1.0 → 1.03)` on background blob, `4s ease-in-out infinite alternate`
- **Card hover:** `transform: translateY(-3px)`, `border-color` brightens, `transition: 0.2s`

---

## Page Structure

Build the page in this exact order:

### 1. `<header>` — Sticky Navigation

**Height:** ~64px  
**Behavior:** Sticky. Adds `backdrop-filter: blur(16px)` + subtle border-bottom after 80px scroll.

**Left:** Logo — violet icon + "Digital Zen" wordmark  
**Center:** Nav links — Features / How it works / FAQ  
**Right:** CTA button — "Add to Chrome — Free"

---

### 2. `#hero` — Hero Section

**Height:** 100vh  
**Layout:** Two-column on desktop (text left, visual right). Stacked on mobile.

**Text column (left):**
- Eyebrow label: `"Focus Extension for Chrome"`
- H1: `"Block Distractions. Focus Deeply."`
- Subheading: `"Digital Zen blocks distracting websites on a schedule and structures your day with a built-in Pomodoro timer."`
- Primary CTA button: `"Add to Chrome — It's Free"` (with Chrome icon + pulse animation)
- Micro-copy under button: `"Free · No account · Works offline"`
- Browser icons row: Chrome, Edge, Brave, Firefox logos (SVG, 24px, muted opacity)

**Visual column (right):**
- Stylized floating screenshot of the extension UI (Focus screen)
- Animated SVG progress ring around it (strokes in violet)
- Soft violet glow blob behind the screenshot
- Subtle breathing scale animation on the blob

---

### 3. `#pain` — Pain Points

**Height:** ~55vh  
**Background:** `--color-surface` (slightly lighter than body)

**H2:** `"Sound Familiar?"`

**4 pain cards in a row** (2×2 on tablet/mobile), each with:
- Icon (Lucide, 28px, violet)
- Short first-person statement (max 12 words)

| Icon | Pain |
|------|------|
| `clock` | Open the browser "for a second" — lose 40 minutes |
| `trending-down` | Workday ends, the main task still isn't done |
| `zap-off` | Every interruption breaks your flow for 20 minutes |
| `settings` | Tried focus apps — too complicated to set up |

---

### 4. `#solution` — Solution

**Height:** ~45vh  
**Layout:** Centered text + 3 feature pills

**H2:** `"Meet Digital Zen — Your Browser Focus Guard"`  
**Body:** `"Set which sites to block and when — then just work. The built-in Pomodoro timer helps you alternate focus and rest without thinking about it."`

**3 pills below the text:**
- `🚫 Smart Blocking`
- `📅 Custom Schedules`
- `🍅 Pomodoro Timer`

---

### 5. `#features` — Core Features

**Height:** ~200vh (4 alternating feature blocks)  
**Layout:** Alternating left/right — odd blocks: image left + text right; even blocks: text left + image right.

Each feature block contains:
- Icon (40px, violet)
- H3 (feature name)
- Body text (2–3 sentences on the benefit, not the feature mechanics)
- Optional secondary detail (small badge or bullet)

**Feature 1 — Flexible Schedules**
- H3: `"Block sites automatically, on your schedule"`
- Body: `"Create focus periods for any time range and any days of the week. Morning routine, work hours, study time — Digital Zen enforces the schedule so you don't have to."`
- Visual: Screenshot of the Focus period screen (home screen)

**Feature 2 — 3 Blocking Modes**
- H3: `"Block, warn, or whitelist — you choose"`
- Body: `"Full block closes the tab instantly. Warning mode shows a reminder you can dismiss. Whitelist mode lets only your approved sites through — everything else is blocked."`
- Visual: Comparison of the three mode icons with labels

**Feature 3 — Built-in Pomodoro**
- H3: `"Structure your day, session by session"`
- Body: `"Work, short break, long break — all configurable. The visual progress bar and browser notifications keep you on track without breaking your concentration."`
- Visual: Screenshot of the Pomodoro screen

**Feature 4 — 100+ Sites Pre-loaded**
- H3: `"All the distracting sites, already in the list"`
- Body: `"Instagram, TikTok, Reddit, Netflix, YouTube and 100+ more are pre-organized into folders. Toggle entire categories on or off in one click."`
- Visual: Website library folder list (illustrated or screenshot)

---

### 6. `#how` — How It Works

**Height:** ~60vh  
**Layout:** Horizontal 3-step stepper on desktop; vertical numbered list on mobile.

**H2:** `"Up and Running in 3 Steps"`

| Step | Icon | Title | Description |
|------|------|-------|-------------|
| 1 | `download` | Install the extension | Click "Add to Chrome" — takes 10 seconds |
| 2 | `list-checks` | Choose sites & schedule | Pick which sites to block and when |
| 3 | `play-circle` | Start your focus session | Hit the toggle and get to work |

**Below the steps:**  
Subtext: `"Setup takes 2 minutes. No account required."`  
Secondary CTA button: `"Add to Chrome — Free"` (ghost style)

---

### 7. `#screenshots` — Screenshot Gallery

**Height:** ~65vh  
**Background:** `--color-surface`

**H2:** `"Digital Zen in Action"`

Gallery of 4 screenshots with thumbnail navigation:
1. Focus screen — active session (Warn mode)
2. Pomodoro screen — running timer
3. Period list view — multiple periods
4. Dark / Light theme comparison

Navigation: dot indicators below. On mobile: swipe carousel (CSS scroll-snap).

---

### 8. `#testimonials` — Social Proof

**Height:** ~50vh

**H2:** `"Built for People Who Value Deep Work"`

**Trust bar (centered row):**
- `★★★★★` Chrome Web Store
- `Open Source · MIT License`
- `Chrome · Edge · Brave · Firefox`

**3 testimonial cards:**

| Avatar | Quote | Name | Role |
|--------|-------|------|------|
| DS | "Finally a focus extension that doesn't feel like bloatware. Installed, configured in 2 minutes, works perfectly." | David S. | Freelance Developer |
| MK | "The warning mode instead of full blocking is exactly what I needed — gentle nudge, not a wall." | Maria K. | UX Designer |
| AT | "Pomodoro + site blocking in one tool. No more switching between apps." | Alex T. | CS Student |

---

### 9. `#faq` — FAQ

**Height:** ~60vh  
**Layout:** Accordion, 2 columns on desktop, 1 column on mobile.

**H2:** `"Frequently Asked Questions"`

| Question | Answer |
|----------|--------|
| Is Digital Zen free? | Yes, completely free and open-source under the MIT license. |
| Which browsers are supported? | Chrome, Edge, Brave, Opera, Vivaldi, and all Chromium-based browsers. Firefox support is also available. |
| Does it track my browsing? | No. All data stays in your browser. Nothing is sent to any server. |
| Can I bypass the block? | In Warn mode, yes — you can dismiss the warning. In Block mode, the tab is closed immediately. |
| Does it work offline? | Yes. Digital Zen works entirely offline with no internet connection required. |
| Can I import/export my settings? | Yes. You can export a full JSON backup and restore it anytime. |

---

### 10. `#cta` — Final CTA Section

**Height:** ~40vh  
**Background:** Violet radial gradient over dark base  

**H2:** `"Start Your First Focus Session Today"`  
**Body:** `"Free. No account. Works 30 seconds after install."`  
**Primary CTA:** `"Install Digital Zen"` (large, full-width on mobile)  
**Micro-copy:** `"★★★★★ · Chrome Web Store · Open Source · MIT"`

---

### 11. `<footer>`

**Height:** ~18vh  
**Layout:** 3-column on desktop, stacked on mobile.

- **Col 1:** Logo + short description (1 line)
- **Col 2:** Links — GitHub, Chrome Web Store, MIT License
- **Col 3:** Built by Denis Saveliev · `github.com/DenHelloWorld`
- **Bottom bar:** `"© 2025 Digital Zen · MIT License · All data stays in your browser"`

---

## Responsive Behavior

| Breakpoint | Key Changes |
|------------|-------------|
| `< 768px` (mobile) | Hero stacks vertically; pain cards single column; features use card layout (no alternating); screenshots become swipe carousel; sticky CTA bar fixed at bottom; footer single column |
| `768–1279px` (tablet) | Hero stacks; pain cards 2×2; features: image top / text bottom; stepper goes vertical; footer 2 columns |
| `≥ 1280px` (desktop) | Full layout as described above |

**Sticky mobile CTA bar:**  
Fixed bottom bar (56px height) with `"Add to Chrome"` button. Visible only on mobile. Has `backdrop-filter` blur + top border. Hidden after user clicks CTA once (`localStorage` flag).

---

## Conversion Elements Checklist

- [ ] Sticky header with CTA button always visible
- [ ] CTA pulse animation on page load (3 pulses, then stops)
- [ ] Micro-copy "Free · No account · Works offline" under every CTA
- [ ] Chrome Web Store badge icon next to CTA
- [ ] Browser compatibility icons row in Hero
- [ ] "Open Source · MIT" trust badge
- [ ] Privacy statement: "All data stays in your browser"
- [ ] CTA repeated 3 times: Hero → How it Works → Final CTA
- [ ] Sticky mobile CTA bar
- [ ] Smooth scroll-reveal animations on all sections
- [ ] IntersectionObserver for scroll animations (no layout shift)

---

## SEO Meta Tags

```html
<title>Digital Zen — Website Blocker & Pomodoro Timer for Chrome</title>
<meta name="description" content="Digital Zen helps you stay focused by blocking distracting websites on a schedule and managing work sessions with a built-in Pomodoro timer. Free Chrome extension.">
<meta name="keywords" content="website blocker chrome, focus extension, pomodoro timer chrome extension, block distracting websites, productivity chrome extension, site blocker for work, block social media chrome">
<meta property="og:title" content="Digital Zen — Block Distractions. Focus Deeply.">
<meta property="og:description" content="Free Chrome extension that blocks distracting sites on a schedule and includes a Pomodoro timer. No account required.">
<link rel="canonical" href="https://your-domain.com">
```

---

## Output Requirements

- Single `index.html` file with all CSS in `<style>` and JS in `<script>`
- Google Fonts loaded via `<link>` in `<head>`
- Icons loaded via CDN (Lucide or Phosphor)
- All screenshots referenced as `img/screenshot-{name}.png` (use placeholder `<div>` styled blocks if images not available)
- Valid, semantic HTML5 (`<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`)
- Accessible: `aria-label` on icon buttons, `alt` on all images, focus-visible styles
- No console errors
- Lighthouse score target: Performance ≥ 90, Accessibility ≥ 95

---

*Prompt prepared for Digital Zen v1.0.1 · Author: Denis Saveliev (DenHelloWorld)*
