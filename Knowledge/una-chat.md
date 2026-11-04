# UNA Chat

> Durable facts for the workspace. Step-by-step Auth0 setup lives in the clone's README. Session memory lives in `brain/`.

Last reinforced 2026-10-28.

## Where the code is

- Clone: `Repos/lab5paradigmas`
- Remote: https://github.com/Camilo-FG/lab5paradigmas.git
- Trunk: `main`
- Same history as `Paradigmas/Lab5/despues` (commit `c39a1b8` when the clone was reviewed)

## What it is

Real-time chat. Express 5 serves one HTML page. Socket.IO broadcasts `Evento-Mensaje-Server`. `libs/unalib.js` sanitizes the author, the color, and the message, and turns image and YouTube URLs into markup. There is no frontend framework.

## US-01

Social login with Auth0, server-side Authorization Code flow. Secrets stay in environment variables (`.env` locally, Vercel project settings in production). The chat and the socket require a session. Tests set `AUTH_DISABLED=true` because they do not have an Auth0 tenant.

See `brain/UNA Chat.md` for the decision and the open deploy steps.
