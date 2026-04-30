## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.
## 2026-04-30 - Massive Discovery Latency Reduction with Preload
**Learning:** Preloading 'canvaskit/chromium/canvaskit.wasm' and 'main.dart.js' with high fetch priority in index.html reduced asset discovery time from ~802ms and ~283ms down to ~24ms in local Playwright testing. This eliminates the waterfall bottleneck where the browser waits for JS execution to find these heavy assets.
**Action:** Always prioritize preloading large, late-discovered assets like WASM bundles and main JS entrypoints in Flutter Web to minimize startup latency.
