# Glow Haus — service pricing site

Static one-page brochure site for Glow Haus (London, Ontario), built from the
design handoff in the parent folder. No build step, no dependencies.

## Files

| File | Purpose |
|---|---|
| `index.html` | The public page (hero, skin treatments, laser hair removal, client testimonials, closing band) |
| `styles.css` | All styles for `index.html` |
| `price-sheet.html` | Print / PDF price sheet (Letter, 0.75in margins) |
| `print.css` | Styles for the price sheet, including `@page` and `@media print` rules |
| `favicon.ico`, `favicon-*.png`, `apple-touch-icon.png`, `site.webmanifest` | Logo favicons and home-screen icon |
| `og-image.png` | Link-preview image (iMessage, WhatsApp, Instagram, Facebook) |

## Run locally

Open `index.html` directly in a browser, or serve the folder:

```sh
cd site
python3 -m http.server 8080
# → http://localhost:8080
```

## Deploy

Upload the contents of `site/` to any static host (Netlify, Vercel, Cloudflare
Pages, GitHub Pages, S3). Set `index.html` as the root document.

## Export the PDF price sheet

Open `price-sheet.html`, press ⌘P / Ctrl+P, choose "Save as PDF", paper size
Letter, margins "Default" (the page sets 0.75in itself), and turn on
"Background graphics" so the cream contact band prints.

## Editing prices or copy

All content lives inline in `index.html` and `price-sheet.html`. Each
treatment is one `.treatment` block; each laser service is one `.laser__row`.
Update both files when prices change so the web page and PDF stay in sync.

## Testimonials

The "Kind words" section quotes real client DMs (Instagram and WhatsApp),
lightly tidied for spelling and with emoji removed. Clients are not named;
each quote is attributed by treatment and channel only. Before going live,
confirm each client is happy to be quoted. To swap a quote, edit the
`.quote` blocks in `index.html`; the first one (`.quote--featured`) is the
large centered one.

## Links

- Book buttons (nav and hero): `tel:+15083199456` (phone call)
- Call or WhatsApp button: `https://wa.me/15083199456`
- Instagram: `https://www.instagram.com/glowhaus_ldn`
