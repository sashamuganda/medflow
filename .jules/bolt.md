## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-13 - Preloading CanvasKit WASM
**Learning:** For optimal Flutter Web performance, preloading the `canvaskit.wasm` binary from the specific variant path (e.g., `canvaskit/chromium/canvaskit.wasm`) as a `fetch` request is as critical as preloading the JS entrypoints.
**Action:** Add `<link rel="preload" href="canvaskit/chromium/canvaskit.wasm" as="fetch" type="application/wasm" crossorigin="anonymous" fetchpriority="high">` to `index.html`.
