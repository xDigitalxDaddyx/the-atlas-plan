# Atlas API — v1

Base URL: `/api/v1`

Protected routes require `Authorization: Bearer <token>` where the token is either a Firebase ID token or the app JWT returned by `POST /auth/verify-phone`.

Errors are always JSON: `{ "error": { "code": "...", "message": "...", "details"?: [...] } }`.

## Health

| Method | Path | Description |
|--------|------|-------------|
| GET | `/health` | Service liveness. Returns `{ status: "ok" }`. |

## Auth

### POST `/auth/verify-phone`
Verify Firebase phone auth; creates the user on first login.

**Body**
```json
{ "idToken": "<firebase_id_token>" }
```
**Response 200**
```json
{ "token": "<jwt>", "user": { "id": "uid", "phone_number": "+1719...", "display_name": null } }
```

## Shops

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| GET | `/shops` | — | List shops. Query: `trade_type`, `shop_type`, `lat`, `lng`, `radius` (miles), `page`, `limit` |
| GET | `/shops/:id` | — | Shop with reviews, aggregate ratings, active jobs |
| POST | `/shops` | ✔ | Create shop profile |
| PUT | `/shops/:id` | ✔ | Update shop profile |

**POST /shops body** (excerpt): `name*`, `address*`, `shop_type*` (dealership|indie|fleet|chain|specialty|mobile), `trade_type*` (12 trade enums), `brands_serviced[]`, `pay_structure` (flat_rate|hourly|salary|hybrid), `pay_range_low/high`, `benefits_*`, `bay_count`, `lift_count`, `lat`, `lng`.

**GET /shops/:id response**
```json
{
  "shop": {
    "id": "...", "name": "Pikes Peak Auto Care", "culture_score": 3.75, "would_return_pct": 100.0,
    "reviews": [ { "id": "...", "rating_pay_structure": 4, "pros": "...", "verified": true } ],
    "review_total": 2,
    "average_ratings": { "pay_structure": 3.5, "management_fairness": 4.0, "tool_policy": 3.0, "work_life_balance": 3.5 },
    "jobs": [ { "id": "...", "title": "Automotive Technician — A/B Level" } ]
  }
}
```

## Reviews

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| GET | `/shops/:id/reviews` | — | Query: `verified`, `page`, `limit`, `sort` (newest|highest|lowest) |
| POST | `/shops/:id/reviews` | ✔ (rate-limited) | Create review. `culture_score` / `would_return_pct` refresh automatically via DB trigger |
| DELETE | `/reviews/:id` | ✔ author only | Delete a review |

**POST body**: `position*`, `trade_type*`, `rating_pay_structure*` (1–5), `rating_management_fairness*`, `rating_tool_policy*`, `rating_work_life_balance*`, `tenure_months`, `pay_rate_at_exit`, `would_return`, `pros` (≤500), `cons` (≤500), `verified`.

## Jobs

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| GET | `/jobs` | — | Query: `trade_type`, `experience_required`, `pay_min`, `pay_max`, `page`, `limit` |
| GET | `/jobs/:id` | — | Job with embedded shop |
| POST | `/jobs` | ✔ shop owner | Create posting |
| PUT | `/jobs/:id` | ✔ shop owner | Update posting (incl. `is_active`) |
| DELETE | `/jobs/:id` | ✔ shop owner | Delete posting |

## Users (all protected)

| Method | Path | Description |
|--------|------|-------------|
| GET | `/users/me` | Profile incl. `saved_shops[]`, `applied_jobs[]` |
| PUT | `/users/me` | Update `display_name`, `trade_specialty`, `experience_level` |
| POST | `/users/save-shop` | Body `{ shop_id }` — add to saved shops (idempotent) |
| POST | `/users/unsave-shop` | Body `{ shop_id }` |
| POST | `/users/apply-job` | Body `{ job_id }` — track application (idempotent) |

## Rate limits
- Global API: 300 req/min/IP
- Auth endpoints: 20 req/15 min/IP
- Review creation: 10 req/hour/IP
