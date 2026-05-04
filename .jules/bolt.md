## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-05-04 - Consolidating discovery with Preloads
**Learning:** Consolidating security meta tags and placing preloads immediately after the `<base>` tag ensures the browser's preload scanner starts fetching critical WASM and JS assets (canvaskit, main.dart.js) before the main HTML is even fully parsed, significantly reducing TTI.
**Action:** Always place preloads for critical assets (WASM/JS/Fonts) at the absolute top of the `<head>` and ensure only a single meta tag exists for CSP and Referrer-Policy to avoid parser confusion.
