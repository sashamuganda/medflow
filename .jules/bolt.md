## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-27 - Reducing Startup Latency and Perceived Load Time
**Learning:** Preloading `canvaskit/chromium/canvaskit.wasm` specifically (if used by the engine) is more effective than generic preloads, as it's the largest critical asset for rendering. Also, a white flash occurs before Flutter's engine initializes if the body background isn't styled.
**Action:** Always preload the specific CanvasKit WASM variant with `high` fetch priority and set the `body` background-color to the brand color in `index.html` inline CSS.
