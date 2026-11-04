# UNA Chat

Real-time chat from Laboratorio 5. Laboratorio 8 adds social login. Created 2026-10-28.

## Current status

2026-10-28: Clone is at `Repos/lab5paradigmas`, commit `c39a1b8` on `main`, even with `origin/main`. US-01 (Auth0) is implemented in the working tree and is not committed. Local `.env` leaves `AUTH0_CONNECTION` empty so Universal Login lists every social connection enabled on the tenant. GitHub is enabled. Google is not configured yet. Jest reported 88 passing tests. A completed login and the Vercel deploy are not done.

## Previous status

2026-10-28, before US-01: Express 5 + Socket.IO chat. Static `index.html`. No authentication. Users typed a display name.

## Stack

- Node.js 22, npm 10. Entry: `server.js`. Port `PORT` or 3000.
- Client: one HTML file, no framework and no CDN.
- Socket event: `Evento-Mensaje-Server` with JSON `{ nombre, mensaje, color, clienteId }`.
- Sanitization: `libs/unalib.js`.
- Tests: Jest (`npm test`) and Playwright (`npm run test:e2e`, port 3100).

## US-01 decision

Auth0 runs on the server with `express-openid-connect` (Authorization Code). The client secret and the session secret stay in environment variables. The browser only receives the display name, email, and picture.

Social providers are enabled in the Auth0 dashboard (Universal Login). `AUTH0_CONNECTION` is optional and, when set, asks Auth0 for that connection directly (for example `google-oauth2`).

The chat page and the socket both require a session when Auth0 env vars are present. `AUTH_DISABLED=true` is for tests only and is ignored when `VERCEL` is set. If the variables are missing, the server shows a setup page instead of the chat.

On Vercel the Socket.IO client must use the WebSocket transport. In-memory broadcast only reaches clients connected to the same function instance.

Last reinforced 2026-10-28.
