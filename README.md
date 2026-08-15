# The Atlas Plan

Transparent job platform + shop reviews for mechanics of every trade. This is the
master repo for the entire project — planning docs, product code, tools, and brand
assets in one place.

> **Working codename: "Atlas".** The final product name hasn't been decided yet.
> The app and code carry the placeholder name `Atlas` so nothing ships with an
> outdated brand. Historical planning and marketing documents from the earlier
> "Wheels" era are kept as-is for reference.

## What's in this repo

```
├── company-identity/                          # Brand identity, fact sheet, ready-to-use blurbs
├── Kimi_Agent_The Atlas Plan/
│   ├── THE ATLAS.txt                          # Master consolidated plan (v1.0)
│   ├── calculator.html                        # "Run The Numbers" pay calculator (single-file)
│   ├── calculator-v2.html, calculator-v3.html # Newer calculator versions
│   ├── TEST-SCENARIOS.md                      # Verified test scenarios for the calculator
│   ├── index.html                             # Strategic innovation brief (rendered)
│   ├── wheels/                                # Product code (working title: Atlas)
│   │   ├── backend/                           # Node.js + Express + PostgreSQL API
│   │   ├── mobile/                            # React Native (Expo) app
│   │   ├── docs/                              # API documentation
│   │   └── verifier/                          # Verifier index (append-only)
│   ├── wheels-brand-assets/                   # Logos, illustrations, app icons (Wheels-era)
│   └── wheels-strategic-brief/                # 10-part strategic brief (Wheels-era)
```

## Quick start

The product code lives in `Kimi_Agent_The Atlas Plan/wheels/`. See its README for
backend + mobile setup.

## Naming notes

- `Atlas` is a placeholder until a final name is chosen. Search-and-replace `Atlas`
  repo-wide when the name is locked in.
- Strategy/marketing documents from the "Wheels" era intentionally still say
  "Wheels" — they're historical planning artifacts, not shipped branding.
