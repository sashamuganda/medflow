## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-05-10 - Preloading CanvasKit WASM
**Learning:** For Flutter Web apps using CanvasKit, preloading the `canvaskit.wasm` binary as a 'fetch' resource with `crossorigin="anonymous"` is critical because the engine fetches it using the Fetch API. Without this, the WASM download only starts after the JS logic has initialized, causing a significant delay.
**Action:** Always include `<link rel="preload" href="canvaskit/chromium/canvaskit.wasm" as="fetch" type="application/wasm" crossorigin="anonymous" fetchpriority="high">` at the top of the `<head>`.
