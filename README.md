# ShopWorth

Transparent job platform + shop reviews for mechanics of every trade. This is the
master repo for the entire project — planning docs, product code, tools, and brand
assets in one place.

> **Brand name: ShopWorth** — "It Has ShopWorth For A Reason." The product name is
> final; `ShopWorth` is used consistently across the codebase, docs, and hosted URLs.

## What's in this repo

```
├── RunTheNumbers.html       # "Run The Numbers" pay calculator (hosted: /RunTheNumbers.html)
├── index.html               # Landing page (hosted: /)
├── strategic-brief.html     # Rendered strategic innovation brief (hosted: /strategic-brief.html)
├── docs/                    # Planning + marketing docs
│   ├── THE SHOPWORTH.txt    #   Master consolidated plan (v1.0)
│   ├── marketing-plan.md    #   Go-to-market & profit plan
│   ├── TEST-SCENARIOS.md    #   Verified calculator test scenarios
│   ├── calculator_prompt.txt
│   └── strategic-brief/     #   10-part strategic brief
├── identity/                # Brand identity, fact sheet, ready-to-use blurbs
├── brand-assets/            # Logos, illustrations, app icons, OG images
└── app/                     # Product code
    ├── backend/             #   Node.js + Express + PostgreSQL API
    ├── mobile/              #   React Native (Expo) app
    ├── docs/                #   API documentation
    └── verifier/            #   Verifier index (append-only)
```

## Hosting (GitHub Pages)

The repo is published at **https://xdigitalxdaddyx.github.io/shopworth/**.
Any push to `main` automatically rebuilds the site.

- Calculator: `https://xdigitalxdaddyx.github.io/shopworth/RunTheNumbers.html`
- Landing page: `https://xdigitalxdaddyx.github.io/shopworth/`

All three calculators have Open Graph tags pointing at a hosted preview image, so
links shared on Facebook (and most chat apps) show a rich preview card. After any
change that affects the preview, force Facebook to re-scrape:

1. Open the [Sharing Debugger](https://developers.facebook.com/tools/debug/)
2. Paste the calculator URL and click **Debug** → **Scrape Again**

## Quick start (product code)

The backend and mobile app live in `app/`. See `app/README.md` for setup.
