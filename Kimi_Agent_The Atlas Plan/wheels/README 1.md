# Atlas

**Know what you're walking into before you walk out.**

Atlas is a transparent job platform and shop review app for **all mechanics** — automotive, motorcycle, aircraft (A&P), diesel/heavy equipment, marine, bicycle, industrial, HVAC, small engine, railroad, ag equipment, elevator. If it has moving parts and someone fixes it, Atlas covers it.

*Working codename — final name TBD.*

## What's in this repo

```
wheels/
├── backend/    # Node.js + Express + PostgreSQL API (Firebase Auth, JWT, Stripe-ready)
├── mobile/     # React Native app (Jobs, Search, Review, Profile)
├── docs/       # API documentation
└── README.md
```

## The problem

Mechanics bounce shop-to-shop chasing pay or culture, discovering the new place is worse **after** burning bridges. There's no Glassdoor for the trades. Tool costs ($30K–80K) make a bad move devastating.

## The solution

- Transparent job listings with real pay ranges, benefits, and culture scores
- Anonymous or verified shop reviews (pay-stub verification)
- Tool Investment Calculator — see what you're REALLY making after tool costs
- Shop owners post jobs and respond to reviews

## Quick start

See `docs/` and each folder's `.env.example`. Full local setup guide (PostgreSQL, Firebase, backend, mobile) is in the project setup documentation (`09-SETUP-README`).

### Backend

```bash
cd backend
cp .env.example .env   # fill in Firebase + PostgreSQL credentials
npm install
npm run migrate
npm run seed
npm run dev            # http://localhost:3000
```

### Mobile

```bash
cd mobile
cp .env.example .env   # fill in API base URL + Firebase client config
npm install
npm start              # Expo: press 'a' for Android, 'i' for iOS
```

## Voice

The app speaks two languages — real talk to mechanics, professional and data-driven to shop owners. The UI is always clean; the voice lives in the microcopy. See the branding guide for the rules.
