# Mercado Fazenda — PWA Setup

You now have 5 files that together form an installable Progressive Web App:

- `mercado_fazenda.html` — the app itself
- `manifest.json` — tells the phone the app's name, icons, colors
- `sw.js` — service worker for offline support
- `icon-192.png` — home-screen icon
- `icon-512.png` — high-res icon

## Important: PWAs need to be hosted online

You **cannot** install a PWA from a file you double-click locally (browsers block service workers on `file://` URLs). You need to host these 5 files together on the web. Here are the easiest free options:

### Option A — GitHub Pages (free, ~5 min)
1. Create a GitHub account if you don't have one
2. Create a new public repository
3. Upload all 5 files to the repo
4. Go to Settings → Pages → enable Pages on the `main` branch
5. Wait ~1 min, then visit `https://<your-username>.github.io/<repo-name>/mercado_fazenda.html`
6. On your phone, open that URL in Chrome (Android) or Safari (iOS), then "Add to Home Screen"

### Option B — Netlify Drop (free, drag-and-drop, no signup needed)
1. Go to https://app.netlify.com/drop
2. Drag the folder containing all 5 files onto the page
3. You get a URL like `https://random-name.netlify.app/mercado_fazenda.html`
4. Open that on your phone and install

### Option C — Vercel, Cloudflare Pages, Firebase Hosting
All similar — sign up, upload, get a URL.

## Installing on your phone

**Android (Chrome):**
- Visit the URL → tap the "📱 Install App" button I added at the bottom-right
- Or: tap the three-dot menu → "Add to Home Screen" / "Install app"

**iPhone (Safari):**
- Visit the URL → tap the Share button (square with up arrow)
- Scroll down → "Add to Home Screen" → "Add"
- iOS doesn't show our install button the same way, but Safari natively supports it

**Desktop (Chrome/Edge):**
- Visit the URL → an install icon appears in the address bar, or use the install button

## After install

- App opens fullscreen, no browser UI
- Works offline (data is cached, your edits are still in localStorage)
- Has a real home-screen icon
- Edits persist exactly like before

## Updating

When you change the HTML and re-upload, the service worker has cache version `mercado-fazenda-v1`. To force users to get the new version, bump that number in `sw.js` (e.g. to `v2`) before re-uploading.
