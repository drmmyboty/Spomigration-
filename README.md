# Spomigration

A local-first playlist metadata migration workspace. The first web app is a static page that runs entirely in the browser.

## Live preview

After enabling GitHub Pages for the `main` branch with the `/(root)` folder, the app will be available at:

`https://drmmyboty.github.io/Spomigration-/`

## Current features

- Import CSV, TSV, or JSON playlist exports.
- Recognize common track, artist, album, duration, Spotify URI, and URL column names.
- Search the imported library.
- Detect and remove duplicate track-and-artist pairs.
- Export a clean CSV or a portable Spomigration JSON file.
- Process files locally in the browser. No upload, account, API key, or backend is required.

## Enable the website

1. Open this repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch **main** and folder **/(root)**, then save.
5. Wait for GitHub Pages to publish the site.

## Important compatibility note

BitChord custom addons expose a track catalogue through routes such as `GET /manifest.json`, `GET /search?q=...`, and `GET /stream/{id}`. That protocol does not define playlist import or migration endpoints.

Spotify's official API can provide catalogue metadata with the required authorization, but it does not provide third-party apps with playable Spotify audio streams. Spomigration therefore does not claim to download Spotify audio or stream Spotify tracks into BitChord.

## Current limitations

- This version imports playlist files that the user already has. It does not sign in to Spotify or fetch a private Spotify playlist.
- It exports metadata, not playable audio URLs.
- Matching tracks to another service requires a separate integration with a provider whose API and terms permit it.

## Privacy

The static app reads selected files in the browser. It does not upload them to a Spomigration server. Do not import files containing information you do not want visible on your own device.

## Project status

The first usable local prototype is in `index.html`. The Spotify-authorized import and destination-provider integrations are not implemented yet.

Spomigration is an independent community project and is not affiliated with Spotify or BitChord.
