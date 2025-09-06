# Architecture

## Web
- Next.js app (React 18)
- API Routes:
  - POST `/api/plaid/create-link-token` → server calls Plaid
  - POST `/api/plaid/exchange-public-token` → store `access_token` (Firestore)
  - GET  `/api/transactions?userId&start&end` → Plaid Transactions API

## Data
- Firestore collections:
  - `plaidItems/{userId}`: `access_token`, `item_id`
  - `climateSummaries/{userId}/{YYYY-MM}`: totals by category (cache)
- Optional: `users/{userId}` for preferences (climate toggle, region)

## Mobile
- Expo app that uses Firebase phone auth and calls the same web API routes
- Optional Plaid RN SDK for native Link flow

## CI/CD
- Web: Vercel (env vars in project settings)
- Mobile: EAS builds (TestFlight/Closed testing)
