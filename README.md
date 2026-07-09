# Vital Chime — Landing + Privacy Page

Single-page, non-scrolling static marketing/info site for the Vital Chime Android app
(`com.nerdsoul.vitalchime`). Serves as the public URL for the Google Play Console
listing — pitches the app and hosts the full privacy policy at a deep-linkable
`#privacy` hash route.

Recreated pixel-for-pixel from the design handoff in the `vital_chime` repo
(`design_handoff_landing_privacy_page/`).

## Preview locally

No build step. Either open directly:

```bash
open index.html
```

or serve it (needed for some browsers to load the Google Fonts stylesheet over `file://`
reliably):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Structure

- `index.html` — the entire site (markup, styles, animations, routing logic).
- `assets/ic_launcher.png` — app icon, used as favicon and in both view headers.

## Config

Three values live at the top of the `<script>` block in `index.html`:

```js
var developerName = 'NerdSoul';
var contactEmail = 't.vamshidhar333@gmail.com';
var playStoreLink = ''; // set once the Play listing is live
```

Setting `playStoreLink` flips the Google Play badge from its disabled "Coming soon"
state to a live link — no other markup changes needed.

## Deploy

Not yet wired to a host. Any static host works (GitHub Pages, Firebase Hosting,
Netlify, ...) — it's a single self-contained `index.html` plus one image asset.
