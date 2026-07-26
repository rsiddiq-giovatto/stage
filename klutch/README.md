# Landing Page Template

## Setup
1. Duplicate this `_template/` folder and rename it for your project
2. Copy your `.npmrc` (Font Awesome auth token) into the folder root
3. Run `npm run setup` to install FA Pro and populate `vendor/fontawesome/`
4. Add your fonts to `fonts/` (TeleNeo-Regular.otf, TeleNeo-Bold.otf, etc.)

## What to update per project
| File | What to change |
|---|---|
| `styles.css` | `--color-primary`, `--color-secondary`, `--color-accent` at the top |
| `styles.css` | `.hero` and `.thankyou-hero` background-image paths |
| `index.html` | All `[PLACEHOLDER]` values |
| `thank-you.html` | All `[PLACEHOLDER]` values |
| `src/` | Logo, background images, partner logos |

## Folder structure
```
your-project/
├── index.html
├── thank-you.html
├── styles.css
├── package.json
├── .npmrc          ← add this yourself, never commit
├── .gitignore
├── fonts/          ← add TeleNeo .otf files
├── src/            ← logo, backgrounds, partner logos
└── vendor/
    └── fontawesome/ ← populated by npm run setup
```
