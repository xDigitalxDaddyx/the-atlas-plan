# The Atlas Plan

Transparent job platform + shop reviews for mechanics of every trade. This is the
master repo for the entire project — planning docs, product code, tools, and brand
assets in one place.

> **Working codename: "Atlas".** The final product name hasn't been decided yet.
> Everything carries the placeholder name `Atlas` so nothing ships with an outdated
> brand. When you pick the real name, the rename is a repo-wide find-replace (see
> below).

## What's in this repo

```
├── calculator.html          # "Run The Numbers" pay calculator (hosted: /calculator.html)
├── calculator-v2.html       # Calculator, blueprint style (hosted: /calculator-v2.html)
├── calculator-v3.html       # Calculator, diagnostic printout style (hosted: /calculator-v3.html)
├── index.html               # Landing page (hosted: /)
├── strategic-brief.html     # Rendered strategic innovation brief (hosted: /strategic-brief.html)
├── docs/                    # Planning + marketing docs
│   ├── THE ATLAS.txt        #   Master consolidated plan (v1.0)
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

The repo is published at **https://xdigitalxdaddyx.github.io/the-atlas-plan/**.
Any push to `main` automatically rebuilds the site.

- Calculator: `https://xdigitalxdaddyx.github.io/the-atlas-plan/calculator.html`
- Landing page: `https://xdigitalxdaddyx.github.io/the-atlas-plan/`

All three calculators have Open Graph tags pointing at a hosted preview image, so
links shared on Facebook (and most chat apps) show a rich preview card. After any
change that affects the preview, force Facebook to re-scrape:

1. Open the [Sharing Debugger](https://developers.facebook.com/tools/debug/)
2. Paste the calculator URL and click **Debug** → **Scrape Again**

## When you pick the final name

1. Decide the name, e.g. `Torque`.
2. Replace `Atlas` / `atlas` repo-wide (case-sensitive passes, then one
   case-insensitive pass for stragglers).
3. Rename the repository on GitHub (Settings → General → Repository name).
4. Update the OG URLs in the three calculator files and `index.html` (the
   `github.io/the-atlas-plan/...` links).
5. Re-scrape in the Facebook Sharing Debugger.

## Quick start (product code)

The backend and mobile app live in `app/`. See `app/README.md` for setup.
