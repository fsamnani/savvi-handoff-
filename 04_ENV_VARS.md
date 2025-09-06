# Environment Variables

## Public (browser)
- `NEXT_PUBLIC_FIREBASE_API_KEY`
- `NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN`
- `NEXT_PUBLIC_FIREBASE_PROJECT_ID`
- `NEXT_PUBLIC_FIREBASE_APP_ID`
- `NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID`

## Server (API Routes / Vercel)
- `PLAID_CLIENT_ID`
- `PLAID_SECRET`
- `PLAID_ENV` (e.g., `sandbox`)
- `FIREBASE_ADMIN_PROJECT_ID`
- `FIREBASE_ADMIN_CLIENT_EMAIL`
- `FIREBASE_ADMIN_PRIVATE_KEY`  (use literal with `\n` line breaks)

## Notes
- Never expose Plaid secrets to the client.
- For local dev, use `.env.local` (Next.js). In Vercel, add each var under Project → Settings → Environment Variables.
