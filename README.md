# NovelMTL Starter (Android-friendly PWA)

This is a starter web app, not a fully automatic universal scraper. It includes:
- Chinese source text input and chapter URL field
- Best-effort browser fetch and common chapter-content selectors
- Best-effort "next chapter" link detection
- Chinese-to-English translation through MyMemory's public endpoint
- Editable local glossary with import/export
- Saved chapters in browser localStorage
- Original/English view toggle and TXT export
- PWA manifest and service worker for install/offline app shell

## Important limitations
1. Arbitrary websites cannot always be fetched from a static browser app. CORS, anti-bot systems, logins, scripts, and site-specific HTML may prevent extraction. If fetch fails, paste the chapter text into the source box.
2. The MyMemory public endpoint has usage limits, may throttle requests, and is not guaranteed to be available. This starter does not provide unlimited free translation.
3. Glossary protection is best-effort. A translation service may alter punctuation or tokens; always review character names and technical terms.
4. This app does not bypass paywalls, logins, DRM, or access restrictions.
5. Data is stored in this browser on this phone. Clearing browser site data can remove saved chapters and glossary; export your glossary and chapters regularly.

## Publish free with GitHub Pages
1. Sign in to GitHub and create a **public** repository named `novelmtl`.
2. Upload all files in this folder to the repository root (not the containing folder).
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main`, folder `/ (root)`, and Save.
6. Wait for GitHub Pages to publish. Your address will look like `https://YOUR-USERNAME.github.io/novelmtl/`.

## Install on Android
1. Open the published address in Chrome.
2. Open Chrome's three-dot menu.
3. Tap **Add to Home screen** or **Install app**.
4. Launch NovelMTL from your home screen.

## Local testing
A PWA service worker requires HTTPS or localhost. You can still open `index.html` locally for basic testing, but installation/offline caching will not work from a `file://` URL.

## Translation endpoint
The app calls `https://api.mymemory.translated.net/get` from the browser. Check that provider's current terms, limits and availability before relying on it for long chapters. Do not add private API keys to this public static repository.
