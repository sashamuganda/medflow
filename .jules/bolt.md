## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-05-20 - Preloading Wasm Assets
**Learning:** To avoid double-downloads when preloading `canvaskit.wasm`, the `<link>` tag must use `as="fetch"` and `crossorigin="anonymous"` to match the fetch request initiated by the Flutter engine. Without these attributes, the browser may download the file twice (once for preload, once for the engine).
**Action:** Always include `as="fetch"` and `crossorigin="anonymous"` when preloading Wasm or other assets fetched via `fetch()` in Flutter Web.
