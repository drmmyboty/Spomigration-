# Spomigration

Spomigration explores moving Spotify playlist and artist metadata into a BitChord-friendly music workflow.

## Important compatibility note

BitChord custom addons expose a track catalogue through three HTTP routes:

- `GET /manifest.json`
- `GET /search?q=...`
- `GET /stream/{id}`

That protocol does not define playlist import, playlist export, or playlist migration endpoints. A BitChord addon also has to return a directly playable media URL from `/stream/{id}`.

Spotify's official API can provide catalogue metadata with the required authorization, but it does not provide third-party apps with playable Spotify audio streams. Therefore, a Spotify-only addon cannot honestly promise playback in BitChord.

## Planned direction

1. Use Spotify's authorized API for artist, album, and playlist metadata where access is permitted.
2. Keep playlist transfer as a separate feature rather than pretending it is part of BitChord's addon protocol.
3. Only resolve tracks through a playback provider whose API and terms permit this use.
4. Implement and publish a BitChord addon only after its search and stream routes can return valid, tested responses.

## Status

Repository setup only. No working addon URL is published yet.
