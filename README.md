# Random Link Redirector

A single-page static web app that instantly redirects visitors to a random link from a list you control. Perfect for NFC tags or QR codes that should open Spotify, YouTube, or any other URL.

## How it works
- `index.html` contains a `links` array with your URLs.
- On page load, JavaScript picks one link at random and redirects the browser using `window.location.replace(...)`.
- If no links are configured, the page shows a friendly message instead of redirecting.

## Edit the links
1. Open `index.html` in a text editor.
2. Find the `links` array near the bottom of the file.
3. Add, remove, or reorder URLs. You can mix any platforms:
   - Spotify track: `https://open.spotify.com/track/...`
   - Spotify episode: `https://open.spotify.com/episode/...`
   - YouTube / YouTube Music: `https://youtube.com/watch?v=...` or `https://music.youtube.com/watch?v=...`
   - Any other URL you want.
4. Save the file. No build step is required.

If the array is empty, visitors will see: `No links configured yet – please add some!`

## Run locally
Because this is a plain HTML file, you can simply open it or serve it from any static server:

- **Option 1: open directly**
  - Double-click `index.html` or open it in your browser.
- **Option 2: serve with Python (ensures correct MIME types)**
  - `python -m http.server 8000`
  - Visit `http://localhost:8000` and you will be redirected.

## Deploy
You can host this file anywhere that serves static assets. Here are a few common options:

- **GitHub Pages**
  1. Commit your changes and push to GitHub.
  2. In your repository settings, enable GitHub Pages for the main branch, root directory.
  3. Access the published URL; every visit will redirect to a random link.
- **Netlify / Vercel**
  1. Create a new site from your repository.
  2. Use the default settings (no build command needed).
  3. Deploy; the root URL will perform the random redirect.
- **Any static host**
  - Upload `index.html`. The root path will instantly redirect users to a random link from your list.

## Notes
- The redirect uses `window.location.replace(...)` so the intermediary page does not stay in browser history.
- To change the visible text on the loading page, edit the headings inside `index.html`.
