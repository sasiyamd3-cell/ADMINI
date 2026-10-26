# MIYORA MD Admin Panel — Vercel Frontend

## Deploy
1. Upload `index.html` and `vercel.json` to the root of a GitHub repository.
2. Import the repository into Vercel. Choose Framework Preset **Other**, no build command, output directory `.`.
3. Open the deployed site. Enter your backend origin in the Backend URL field (for example `https://YOUR-HEROKU-APP.herokuapp.com`) and sign in with the existing backend admin password.
4. Configure backend CORS to allow your Vercel domain.

## Channel removal
The Channel Manager has a Remove button. It calls `DELETE /code/api/admin/channels/:jid` with the admin token and `x-confirm: yes`. Your backend must implement this protected endpoint and remove the channel from persisted reaction configuration. If the route is missing, the UI will show an error; frontend-only changes cannot delete backend-stored records.

## Important
This ZIP contains the responsive frontend, not your bot backend/database. Existing features work only where corresponding backend routes already exist. Never put passwords or backend secrets in frontend code. Enforce owner authorization, token expiry, rate limiting, input validation, HTTPS, and restrictive CORS on the backend.

The frontend expects the existing routes below `/code/api/admin` for login/logout, stats, number analytics, system metrics, wallets/coins, channels, API keys, webhooks, alerts, and analytics.
