# QRnuupsutin

A free, browser-only QR code generator with your own logo in the middle.

- Paste a link → the QR code updates live
- Add a logo by clicking, dragging & dropping, or pasting (⌘/Ctrl+V). The logo keeps its original colors.
- The logo box always stays in the middle of the code. Inside it you can drag the logo to position it and zoom in or out with the mouse wheel, a trackpad or touch pinch, or the zoom slider. Arrow keys nudge it, +/− zoom, 0 resets.
- Choose square or dot pixels. In dot style, the corner and alignment squares that scanners rely on stay solid (rounded).
- Pick the QR color and background (or transparent)
- Download as PNG (512 – 4096 px)

Everything runs in the visitor's browser. Nothing is uploaded and there is no server, so hosting is free.
The box in the middle of every code is left empty for the logo. The logo is cut off at the box edge, so moving or zooming it never covers the code. Codes use the highest error correction level (H, ~30%), and before showing a code the app decodes it itself (with the area empty and with your logo in it). If it doesn't scan, the app switches to a denser QR version until it does. If no version scans, download is disabled and the app says what to change.

## Run locally

Open `index.html` in a browser. No build step and nothing to install.

## Publish for free with GitHub Pages

1. Push this repo to GitHub (`git push origin main`).
2. On GitHub, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, then pick branch `main` and folder `/ (root)`. Save.
4. After about a minute the site is live at `https://teeqxq.github.io/QRnuupsutin/`.

The repo must be public for free GitHub Pages.

### Optional: your own domain

A domain costs roughly €10–15 per year from any registrar (Cloudflare, Porkbun, Namecheap…). Hosting stays free.

1. In **Settings → Pages → Custom domain**, enter e.g. `qr.example.com` and save. GitHub adds a `CNAME` file to the repo.
2. At your registrar, add a DNS record:
   - subdomain (`qr.example.com`): `CNAME` → `teeqxq.github.io`
   - apex domain (`example.com`): `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. Once DNS works, tick **Enforce HTTPS**.

## Files

- `index.html` – the whole app (HTML, CSS, JS)
- `vendor/qrcode.min.js` – [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) 1.4.4 (MIT), creates the codes
- `vendor/jsQR.min.js` – [jsQR](https://github.com/cozmo/jsQR) 1.4.0 (Apache-2.0), checks each code scans

Both libraries are included in the repo so the site doesn't depend on any other website.
