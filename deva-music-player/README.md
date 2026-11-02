# Deva Music Player (offline-first PWA)

Run: serve this folder over HTTPS or localhost (service workers and file access need it), e.g.
`python3 -m http.server 8080` then open http://localhost:8080 in Chrome or Edge, and install it (address-bar icon / "Install app").
After the first load it reopens with no internet. On Android: open the hosted URL in Chrome > menu > Install app.

Adding music
- Add songs / Add folder: on desktop Chrome/Edge files are referenced in place (no copy) via persistent file handles; the browser may ask permission again after a restart.
- On Android Chrome (no folder handles) songs are copied into the app's private storage (IndexedDB), so they always play offline. Storage use is shown in Settings.

Data (IndexedDB "deva"): tracks, artwork, playlists, favorites, play history, queue, last song + position, settings.
Background playback uses the Media Session API (lock-screen controls). Update the app by bumping `V` in sw.js.
