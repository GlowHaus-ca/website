# Handoff: Glow Haus Service Pricing Page

## Overview
A single-page marketing/price-list site for **Glow Haus**, a beauty studio in London, Ontario offering advanced skin treatments and laser hair removal. The page presents two price lists (skin treatments, laser hair removal) with booking CTAs via phone/WhatsApp and Instagram DM. A separate print-optimized version exists for PDF/paper price sheets.

## About the Design Files
The files in this bundle are **design references created in HTML** — prototypes showing the intended look and behavior, not production code to copy directly. The task is to **recreate these designs in the target codebase's existing environment** (React, Next.js, Vue, plain static site, etc.) using its established patterns. If no environment exists yet, a simple static site or lightweight framework (e.g. Astro/Next.js static export) is appropriate — this is a one-page brochure site.

Note: `Glow Haus.dc.html` uses a small templating runtime (`support.js`, `{{ }}` holes, `<sc-for>` loops, a `Component` logic class in a `data-dc-script` block). Ignore the runtime — the data and markup patterns are all documented below. `Glow Haus-print.dc.html` is plain markup inside a `<doc-page>` print shell.

## Fidelity
**High-fidelity.** Colors, typography, spacing, and copy are final. Recreate pixel-perfectly. (The design intentionally does NOT use the Industry design system attached to the project — the client chose this custom "spa minimal" direction instead.)

## Screens / Views

### 1. Main page (`Glow Haus.dc.html`)
One scrolling page, max content width 1000px centered, 24px side padding, background `#faf7f2`.

**Nav bar** — flex row, gap 32px, padding 28px 24px:
- Brand "Glow Haus" — Cormorant Garamond 26px/600, letter-spacing 0.04em
- Spacer (flex:1)
- Links "Skin" (#skin), "Laser" (#laser) — Jost 14px, uppercase, letter-spacing 0.14em, color `#7d6a55`, hover `#2e2a26`
- "Book" pill button — 1px solid `#2e2a26` border, padding 10px 22px, border-radius 999px; hover: fill `#2e2a26`, text `#faf7f2`. Links to WhatsApp (see Interactions).

**Hero** — centered text, padding 88px 0 72px:
- Kicker "LONDON, ONTARIO" — 13px, letter-spacing 0.28em, uppercase, `#7d6a55`, margin-bottom 24px
- H1 "Your skin, / *in its best light.*" (second line italic, weight 400) — Cormorant Garamond 500, clamp(44px, 7vw, 84px), line-height 1.08
- Paragraph: "Advanced skin treatments and laser hair removal. Simple per-session pricing — call, WhatsApp, or DM to begin your skin care journey." — 17px/30px, max-width 52ch, `#5c554d`, margin-top 28px
- CTA row (flex, gap 14px, centered, margin-top 36px):
  - Primary pill "BOOK A SESSION" — bg `#2e2a26`, text `#faf7f2`, padding 14px 32px, radius 999px, 14px uppercase ls 0.1em; hover bg `#7d6a55`
  - Secondary pill "@GLOWHAUS_LDN" — 1px solid `#cfc4b5` border, text `#2e2a26`, same padding/radius; links to Instagram

**Skin treatments section** (`#skin`) — padding 56px 0, top border 1px `#e5dccf`:
- H2 "Skin treatments" — Cormorant Garamond 500, 36px
- Rows: CSS grid `minmax(0,5fr) minmax(0,6fr) auto`, gap 12px 40px, baseline-aligned, padding 26px 0, bottom border 1px `#e5dccf`
  - Name — Cormorant Garamond 600, 24px
  - Description — Jost 15px/25px, `#5c554d`
  - Price — 19px, `#7d6a55`

| Name | Description | Price |
|---|---|---|
| BioRe Peel | A no-peel chemical peel — exfoliates, stimulates collagen and brightens with little to no downtime. | $150 |
| Zena Algae Peel | A natural algae-based resurfacing treatment that renews texture and leaves skin visibly fresher. | $150 |
| Microneedling | Fine micro-channels trigger the skin's own repair — smoother texture, softer scarring, firmer skin. | $100 |

**Laser hair removal section** (`#laser`) — padding 40px 0 72px:
- H2 "Laser hair removal" — Cormorant Garamond 500, 36px; sub-line "Per session." 14px `#5c554d`
- Two-column responsive grid: `repeat(auto-fit, minmax(260px, 1fr))`, column gap 56px
- Rows: flex space-between, baseline, padding 18px 0, bottom border 1px `#e5dccf`; name 16px, price 17px `#7d6a55`

| Service | Price |
|---|---|
| Full body — head to toe | $180 |
| Full face | $40 |
| Brazilian | $50 |
| Under arms | $35 |
| Legs | $65 |
| Arms | $60 |

**Closing band** — full-bleed bg `#efe7da`, inner content 1000px, padding 72px 24px, centered:
- H3 "Begin your skin care journey." — Cormorant Garamond 500, clamp(30px, 4vw, 48px)
- Primary pill "CALL OR WHATSAPP" (same style as hero primary), margin-top 28px
- Footer line "GLOW HAUS · LONDON, ONTARIO · +1 (647) 449-3957 · @GLOWHAUS_LDN" — 13px, ls 0.2em, uppercase, `#7d6a55`, margin-top 36px

### 2. Print price sheet (`Glow Haus-print.dc.html`)
Letter-size flowing document, 0.75in margins, same palette/type. Centered header (kicker, "Glow Haus" title 52px, intro paragraph with phone number), then the two price lists as compact ruled rows, closing with an `#efe7da` contact band. Rows use `break-inside: avoid`. Use for PDF/print export only.

## Interactions & Behavior
- "Book" / "Book a session" / "Call or WhatsApp" → `https://wa.me/16474493957` (WhatsApp deep link for +1 647 449-3957)
- Instagram links → `https://www.instagram.com/glowhaus_ldn?stkn=MXQ2MnF6cHFqMnBnNA%3D%3D` — open in new tab (`target="_blank" rel="noopener"`)
- "Skin" / "Laser" nav links → smooth anchor scroll to sections
- Hover states as specified per button; text links `#7d6a55` → `#2e2a26`
- No forms, no loading/error states. Fully static.
- Responsive: content max-width + clamp() type; laser grid collapses to one column below ~570px; CTA rows wrap.

## State Management
None required — static content. Prices/services could come from a small config/CMS if desired; the data tables above are the source of truth.

## Design Tokens
Colors:
- Background: `#faf7f2` (cream)
- Band/tint: `#efe7da`
- Ink: `#2e2a26`
- Muted text: `#5c554d`
- Accent (taupe): `#7d6a55`
- Hairline borders: `#e5dccf`
- Secondary border: `#cfc4b5`

Typography (Google Fonts):
- Headings: **Cormorant Garamond** 400/500/600 (+ italic)
- Body/UI: **Jost** 300/400/500; body default weight 300
- UI labels: uppercase, letter-spacing 0.1–0.28em

Shape & spacing:
- Buttons: pill radius (999px), padding 14px 32px (nav variant 10px 22px)
- No shadows, no rounded cards — hairline rules only
- Section padding: 56–88px vertical; row padding 18–26px

## Assets
- Google Fonts only (Cormorant Garamond, Jost). No images shipped; if photos are added later they come from the client's Instagram feed.

## Files
- `Glow Haus.dc.html` — main page design reference
- `Glow Haus-print.dc.html` — print/PDF price-sheet variant
- `support.js`, `doc-page.js`, `image-slot.js` — prototype runtime helpers; reference only, do not port
