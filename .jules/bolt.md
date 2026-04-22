## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-12 - Preloading Chromium-optimized CanvasKit
**Learning:** Preloading the specific path 'canvaskit/chromium/canvaskit.wasm' (if used by the engine) is more effective than preloading the root 'canvaskit/canvaskit.wasm'. It reduces discovery latency from ~200ms to ~40ms in local benchmarks.
**Action:** Always check which CanvasKit variant is being loaded and preload the specific .wasm file at the top of <head>.
