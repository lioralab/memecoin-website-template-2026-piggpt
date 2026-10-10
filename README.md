<div align="center">

# Memecoin Website Design 2026 — PIGGPT

### A dark, motion-led landing page concept for Solana memecoins.

[![Live preview](https://img.shields.io/badge/%E2%9C%93_live_preview-memecoin--website--design--2026--piggpt.netlify.app-FF3E9A?style=for-the-badge)](https://memecoin-website-design-2026-piggpt.netlify.app/)
[![Accessibility](https://img.shields.io/badge/a11y-WCAG%202.2%20AA-4F7A00?style=flat-square)](#accessibility)
[![Responsive](https://img.shields.io/badge/responsive-320%E2%86%921920px-35E8FF?style=flat-square)](#responsive-behaviour)
[![Dependencies](https://img.shields.io/badge/dependencies-none-B6FF3B?style=flat-square)](#built-with)
[![No build step](https://img.shields.io/badge/build-none%20required-D946EF?style=flat-square)](#built-with)

[**→ Open the live design**](https://memecoin-website-design-2026-piggpt.netlify.app/)

</div>

---

![Hero](preview-01-hero.jpg)

> **A design concept, not a live token.** This is a showcase page for a fictional token called PIGGPT, built to demonstrate an art direction: near-black canvas, acid accents, a mascot as the hero, and motion that carries meaning. The contract address field ships deliberately empty. Nothing on this page is an offer, a promotion, or financial advice.

---

## Contents

- [The concept](#the-concept)
- [Design system](#design-system)
- [Page anatomy](#page-anatomy)
- [Motion language](#motion-language)
- [Craft details](#craft-details)
- [Responsive behaviour](#responsive-behaviour)
- [Accessibility](#accessibility)
- [Built with](#built-with)
- [The service](#the-service)
- [Process](#process)
- [Packages](#packages)
- [Enquiries](#enquiries)
- [Rights](#rights)

---

## The concept

Most memecoin sites are a white page, a wallet button, and a chart. That reads as disposable, and it gives the project no face.

This concept treats the token as a **character**. The mascot is not decoration in the corner — it occupies the centre of the first screen at roughly the same visual weight as the wordmark. Everything else in the art direction supports that one decision: the canvas is almost black so the character carries the colour, the accent palette is deliberately acid (`#B6FF3B`, `#35E8FF`) against magenta, and the type is wide and confident rather than crypto-loud.

The tone underneath is *competent*, not *hype*. The roadmap section literally reads *"No vague promises about global adoption."* The risk disclosure sits in the footer, not hidden. When the contract address is missing the interface says so plainly instead of rendering a placeholder that looks real.

That restraint is the part worth copying. A design that reads as trustworthy gets further than one that shouts.

## Design system

**Palette**

| Role | Token | Hex | Where it earns its place |
|---|---|---|---|
| Canvas | `--bg` | `#07060C` | Near-black with a violet cast, so the magenta feels warm against it |
| Surface | `--surface` | `#100D1B` | Cards, one step up from the canvas |
| Primary text | `--text` | `#F4F0FF` | Soft white — pure white glares on a dark field |
| Secondary | `--muted` | `#9E95BA` | Body copy at 5.77:1 on canvas |
| Tertiary | `--muted-2` | `#948CB0` | Labels at 10–12px, tuned to 5.33:1 |
| Signature | `--pink` | `#FF3E9A` | The mascot, the primary button, the wordmark |
| Signature light | `--pink-2` | `#FF7AC0` | Pig snout, soft fills |
| Gradient mid | `--magenta` | `#D946EF` | Pink → magenta → violet gradient |
| Gradient end | `--violet` | `#8B5CF6` | Gradient terminus |
| Signal | `--acid` | `#B6FF3B` | Live indicators, kickers, "COMPLETE" badges |
| Signal alt | `--cyan` | `#35E8FF` | Secondary signal, the particle field |
| Warning | `--amber` | `#FFB020` | Risk disclosure accents |

Two gradients do most of the work — `pink → magenta → violet` for display type, and `acid → cyan` for anything live or active. Restraint there is what keeps it from looking like a casino.

**Typography**

| Role | Face | Use |
|---|---|---|
| Display | Space Grotesk | Headlines, the wordmark |
| Body | Inter | Paragraphs, UI |
| Data | JetBrains Mono | Contract address, token figures, phase tags |

Three families is generous for a landing page. Space Grotesk carries the personality, Inter stays invisible, and JetBrains Mono signals "this is a number, read it exactly" for contract addresses and supply figures.

**Grid** — 1240px maximum, `clamp(20px, 5vw, 48px)` gutters, 18 / 28 / 40px radii.

## Page anatomy

Eight sections, each doing one job.

| # | Section | Design intent |
|---|---|---|
| — | **Hero** | Two-column split. Wordmark and contract address left, mascot in an orbital ring system right. Two counter-rotating rings carry floating data chips. |
| 01 | **Origin** | Four narrative chapters on a numbered spine. Large outlined numerals, generous leading — this is the section that gives the project a story instead of a ticker. |
| 02 | **Tokenomics** | Animated SVG donut chart that draws itself on scroll, five allocation rows with proportional bars, six spec tiles beneath. The percentages are readable as text, not only as colour. |
| 03 | **Airdrop** | A single strong card. Oversized allocation figure, eligibility checklist, three wave bars for distribution tiers, and a warning strip. |
| 04 | **How to Buy** | Four numbered step cards with inline SVG icons, 3D tilt on hover. Deliberately short — the job is reducing friction, not explaining everything. |
| 05 | **Roadmap** | A vertical timeline with a gradient rail that fills as you scroll. Nodes sit on the axis; state badges read `COMPLETE` / `IN PROGRESS`. Cards cap at 860px so text never strays. |
| 06 | **Community** | Four social cards plus a live-status strip. |
| 07 | **FAQ** | Six `<details>` disclosures, one open at a time. Answers the "is this a scam" question directly rather than hiding it. |
| — | **Footer** | Brand, nav, and a full risk disclosure. |

![Tokenomics](preview-02-tokenomics.jpg)

![Roadmap](preview-03-roadmap.jpg)

## Motion language

Motion is used to explain state, never to fill time. Five ideas carry the whole page:

**Boot sequence** — a preloader with a progress log resolves before the hero paints. It sets the expectation that this is a designed artefact rather than a template.

**Orbital rings** — two rings counter-rotate around the mascot at 26s and 38s, each carrying a data chip. The chips stay upright because they counter-rotate against their parent — an easy thing to get wrong, and visible immediately when you don't.

**Scroll-linked reveal** — sections rise and fade in as they enter the viewport. The roadmap rail fills progressively with scroll position.

**Data that draws itself** — the donut chart animates its stroke on entry; figures count up; wave bars fill left to right.

**Micro-interaction** — magnetic buttons that lean toward the cursor, 3D tilt on cards, ripple feedback on press, a custom cursor with a trailing ring.

Every one of these is gated on `prefers-reduced-motion`. On a reduced-motion device the preloader is skipped, the particle canvas never initialises, the cursor is replaced by the system one, the scramble effect is skipped, and all content renders immediately.

## Craft details

The things that separate a considered design from a busy one:

- **Headlines use `text-wrap:balance`**, so a two-line heading splits evenly instead of orphaning a single word.
- **Step cards reserve two lines for their titles**, so the body copy underneath aligns across all four cards.
- **Colour is never the only signal.** Allocation rows carry text labels, roadmap states carry badges.
- **The contract address is a `<code>` element** in a monospace face with a copy affordance — treated as data to be read exactly, not as prose.
- **If the contract address is unset, the interface says so** — *"Awaiting launch — contract address not published yet"* — and the copy buttons explain why rather than silently copying nothing.
- **The print stylesheet is designed, not inherited.** Ctrl-P produces a readable document: white ground, dark text, single-column grids, roadmap flattened to a list. Every print colour was chosen to clear 4.5:1 on paper.
- **Works without JavaScript.** A `<noscript>` block neutralises the preloader and reveals all content.

## Responsive behaviour

Verified at 320, 375, 768, 1080, 1440 and 1920px with **zero horizontal overflow** at every width.

| Breakpoint | Changes |
|---|---|
| ≤ 1080px | Nav collapses to a drawer; hero becomes single-column with the mascot first; tokenomics specs, buy steps and socials go to 2–3 columns |
| ≤ 640px | Stats and steps stack to one column; specs to two; the allocation rows reflow; the orbital rings are removed rather than shrunk |
| ≤ 400px | The wordmark text collapses to the logo mark alone |

Dropping the orbit rings below 640px instead of scaling them down is the right call — a shrunken orbital system reads as an error, while its absence reads as intentional.

## Accessibility

Audited against WCAG 2.2 Level AA with axe-core 4.12.1: **0 violations, 42 passes**.

- All body text clears 4.5:1; large text clears 3:1. Every ratio was measured against real rendered pixels, not inferred from token values.
- Interactive targets are at least 44×44px.
- Skip-to-content link, visible focus ring on every control.
- The mobile drawer traps focus, marks background content `inert`, and closes on Escape.
- Full `prefers-reduced-motion` support.
- Semantic landmarks and a single valid `<h1>`.

A design that excludes people is not a finished design. This one is built to pass on the first audit, not the third.

## Built with

HTML, CSS and vanilla JavaScript. **No framework, no bundler, no npm install, no runtime dependency, no build step.**

That constraint is deliberate and it is part of the offer. There is no hydration cost, no client-side routing, and no dependency rot. The page is a static file you can host anywhere in under a minute.

The mascot, the donut chart and every icon are inline SVG — no image requests, infinitely crisp, recolourable from the token variables.

---

# The service

**I design memecoin and crypto-project websites.** This page is the portfolio piece: a complete art direction, built and shipped rather than mocked up.

## What I can do

| | |
|---|---|
| **Landing page design** | A full single-page site like this one — hero, story, tokenomics, roadmap, FAQ, disclosure |
| **Art direction** | Palette, type pairing, mascot and iconography, motion language — a system you can extend across pages |
| **Character & mascot** | Custom SVG illustration built for the project, like the pig in this design |
| **Rebrand** | New identity and design system applied to an existing site |
| **Performance & accessibility** | Bringing an existing build up to WCAG AA, Core Web Vitals and print quality |
| **Deployment** | Static hosting on Netlify, Vercel, Cloudflare Pages or GitHub Pages |

## What I won't do

Being clear about this early saves everyone time:

- I don't write or promise price predictions, "next 100x" claims, or guaranteed returns. Those are financial promotion in most jurisdictions, and I won't put them on a page.
- I don't create fake testimonials, fabricated holder counts presented as live, or invented partnerships.
- I don't build dark patterns — fake urgency timers, confirm-overrides on cancel buttons, or anything designed to trap a wallet connection.

A landing page is marketing material, and in the UK, the EU under MiFID II and comparable regimes elsewhere, marketing a security is regulated. Knowing that boundary is part of the job.

## Process

**1. Brief** — I ask what the project is, who it's for, and what the page must accomplish. Twenty minutes.

**2. Direction** — I propose one art direction, not three options to choose between endlessly. Palette, type, mascot approach, motion language, and a wireframe of the section order.

**3. Build** — Full page, built and responsive, not a static mockup. You review on the live URL.

**4. Refine** — Two rounds of revision on spacing, copy, motion timing and colour balance.

**5. Handoff** — You get the source, the deploy, and a short guide to the configuration. No lock-in, no ongoing fee to change a colour.

---

## Packages

<!-- Replace the placeholders below with your real terms before publishing. -->

| | Concept | Standard | Bespoke |
|---|---|---|---|
| Sections | Up to 4 | Up to 8 | Unlimited |
| Custom mascot | — | Simple SVG | Fully original |
| Art direction | Reuse | New palette + type | New palette, type, illustration system |
| Motion | Basic | Full | Full + custom transitions |
| Revisions | 1 | 2 | 3 |
| Delivery | `[days]` | `[days]` | `[days]` |
| Price | `[amount]` | `[amount]` | `[amount]` |

Custom work quoted separately. Payment terms `[50% upfront / 50% on delivery]`.

## Enquiries

<!-- Replace with your real contact details before publishing. -->

Open an issue on this repository, or reach me directly:

- Email: `[your@email.com]`
- Telegram: `[your handle]`
- X: `[your handle]`

**Please don't open a public issue with your contract address in it.** Send it privately once we've agreed to work together.

---

## Rights

This design is a **showcase concept** created to demonstrate art direction and front-end craft. It is not affiliated with, endorsed by, or connected to PIGGPT or any other token, protocol, exchange or organisation. All names and figures are fictional.

The code in this repository is released under `[LICENSE — add one before publishing]`. The PIGGPT name, artwork and concept remain the property of their creator.

**Nothing here is financial, investment, legal or tax advice.** Cryptocurrency assets are volatile and can lose their entire value.

---

<div align="center">
  <sub>Design showcase · <a href="https://memecoin-website-design-2026-piggpt.netlify.app/">Live preview</a> · <a href="AUDIT.md">Accessibility audit</a></sub>
</div>
