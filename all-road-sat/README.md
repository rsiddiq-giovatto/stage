# ALL ROAD SAT — Landing Page

Built from the Pegatron `_template`, following the same layout as the other
landing pages (connected501 etc.). Performance-optimized from the start.

## Performance notes
- **Fonts**: all OTF/TTC sources converted to WOFF2 (primary) with the original
  OTF kept as a fallback `src`, all with `font-display: swap`. Avenir Next was a
  `.ttc` collection — each weight was extracted into its own WOFF2 + OTF.
  No external font CDN is used.
- **Images**: print-CMYK assets from the source artwork were converted to web
  sRGB. The hero was resized to 1920px wide. JPEGs saved at quality 82; PNG
  logos (with transparency) saved with `compress_level=9`.
- **Font Awesome**: `all.min.css` is NOT linked. Only the icons actually used
  (globe, envelope, phone, lock) are declared in
  `vendor/fontawesome/css/fa-minimal.css` using the `--fa` custom-property
  pattern, served by a single `fa-regular-400.woff2`.

## Per-project values
| File | What changed |
|---|---|
| `styles.css` | Brand colors (gold / dark / T-Mobile magenta), self-hosted @font-face |
| `index.html` | ALL ROAD SAT copy, logo, hero, SOS promo, about, contact |
| `thank-you.html` | ALL ROAD SAT confirmation + contact |
| `src/` | hero, logo, SOS button, field worker, partner logos |

## Lead form
Posts to the shared Giovatto backend with `source: 'allroadsat'`.
