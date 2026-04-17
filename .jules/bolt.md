## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-17 - Preloading CanvasKit WASM
**Learning:** For Flutter Web apps using local CanvasKit, preloading `canvaskit.wasm` with high priority significantly reduces the engine initialization delay. Browsers often discover this large binary late because it's triggered by `canvaskit.js` which is itself triggered by `flutter_bootstrap.js`.
**Action:** Add `<link rel="preload" href="canvaskit/canvaskit.wasm" as="fetch" type="application/wasm" crossorigin="anonymous" fetchpriority="high">` to `index.html` at the top of the `<head>`.
