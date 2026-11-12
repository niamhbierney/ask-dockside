# Ask Dockside

A single-page customer chatbot demo for the fictional Dockside Paddle Co. at Grand Canal Dock, Dublin.

## Live data sources

- Sessions CSV: `https://bdaib-hub.pages.dev/data/dockside/sessions.csv` (refreshed every five minutes)
- Current weather: Open-Meteo forecast API for Grand Canal Dock (refreshed every five minutes)
- Knowledge brain: `https://bdaib-hub.pages.dev/brain/chat`

## Run locally

The app is a static single-file site. From this directory, run:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`.

A local HTTP server is recommended instead of opening the file directly with `file://`, because browsers restrict cross-origin requests from local files.

## Publish with GitHub Pages

In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then save. GitHub Pages will publish `index.html` at:

`https://niamhbierney.github.io/ask-dockside/`

## Important notes

- The wind, gust and precipitation thresholds in the UI are provisional demonstration values, not operational safety rules. Dockside staff must make and communicate actual go/no-go decisions.
- The app does not create bookings or confirm reservations.
- The brain endpoint request/response contract must be verified against the live endpoint. The page currently sends a JSON POST with a `message` field and supports common response fields (`reply`, `response`, `answer`, `message`, and OpenAI-style `choices`).
- Browser access depends on the remote endpoints allowing CORS from the local origin and the published GitHub Pages origin.
