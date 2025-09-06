# Requirements

## Platforms
- Web: Next.js (Vercel)
- Mobile: Expo (iOS/Android) consuming same backend

## Core Features
- Auth: Firebase Phone OTP
- Bank link: Plaid Link → token exchange on server → fetch Transactions
- Transactions: list, basic categorization (Plaid PFC)
- Budgets: per category, progress bars, over-budget flags
- Bills: due date, autopay toggle, paid/unpaid
- Goals: target amount, progress
- Insights: monthly income/expense summary, top category

## Climate Extensions
- Spend-based emissions per category using published factors (see `06_CLIMATE_METHOD.md`)
- Electricity (Utilities) override via kWh and US region when provided; otherwise fallback to spend-based
- Insights panel: total kgCO₂e, top category driver, 2 reduction tips
- “About Climate” modal describing method + limitations + sources
- Settings: toggle climate insights, set electricity region (optional)

## Compliance
- Privacy & Terms pages (links from app + store listings)
- In-app account deletion (delete Firestore docs + user)
