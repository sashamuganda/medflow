## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2025-06-01 - Consolidating Meta Tags and Preloading Assets
**Learning:** Duplicate Content-Security-Policy and Referrer meta tags in index.html can lead to confusing behavior and slight overhead as the browser must intersect policies. Preloading canvaskit.wasm and critical fonts significantly reduces resource discovery offsets in Flutter Web applications.
**Action:** Always scan for and consolidate redundant meta tags. Use <link rel="preload"> with fetchpriority="high" for the WASM engine and primary font files to minimize the time to first meaningful paint.
