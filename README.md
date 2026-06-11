# Evidentum Local

The installable edition of Evidentum — a self-contained systematic review search
and appraisal workbench. Same single-file core, plus: installable as a desktop /
home-screen app (PWA), offline-capable shell, polished typography and opening
screen, and scaffolding for OpenAI account sign-in.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire application (single file, as always) |
| `manifest.webmanifest` | Makes the app installable (name, icons, colours) |
| `sw.js` | Service worker — offline shell caching (required to be a separate file by the platform; the only exception to single-file) |

## Deploy & install (GitHub Pages)

1. Put these three files in a folder of your repo (e.g. `/local`), or a dedicated repo.
2. Enable GitHub Pages (Settings → Pages → deploy from branch).
3. Open the published URL in Chrome / Edge / Safari.
4. Desktop: click the install icon in the address bar ("Install Evidentum Local").
   Mobile: Share → Add to Home Screen.

The app then launches in its own window, with its own dock/taskbar icon, and the
shell opens offline. Updates ship automatically next time the user is online —
just push to GitHub.

## Sign in with ChatGPT (OpenAI account)

OpenAI's third-party sign-in ("Sign in with ChatGPT") is a **gated program**:
you apply via OpenAI's developer interest form, register the app's URL, and
receive an OAuth client ID.

The full OAuth 2.0 + PKCE flow is already built in. Once you have a client ID:
Settings → "OpenAI Account" → paste the client ID → the **Sign in with ChatGPT**
button goes live. Until then, OpenAI / Anthropic API keys work exactly as in the
web edition.

## Notes

- All data (keys, projects, pool, settings) stays in the browser's local storage
  on the user's machine. Nothing is sent anywhere except the search APIs and the
  AI provider the user configures.
- The splash screen shows once per session; click anywhere to skip.
