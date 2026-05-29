## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2025-05-14 - Preloading fonts and engine binaries
**Learning:** Preloading the primary Roboto font variant and the CanvasKit WASM binary with high fetch priority significantly reduces resource discovery offsets (from >1s to <70ms for fonts). Consolidating CSP headers also ensures consistency and avoids browser-enforced intersections of multiple policies.
**Action:** Always identify and preload the first-rendered font and critical engine binaries (canvaskit.wasm) in Flutter Web apps to minimize First Contentful Paint.
