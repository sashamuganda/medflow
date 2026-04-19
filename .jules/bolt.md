## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-19 - Preloading CanvasKit WASM
**Learning:** Preloading the 6.9MB CanvasKit WASM file significantly reduces the time it takes for the browser to discover and start fetching this critical asset, which is otherwise only requested after the Flutter engine starts initializing.
**Action:** Always include <link rel="preload" as="fetch" type="application/wasm" crossorigin="anonymous"> for local CanvasKit WASM in Flutter Web projects to optimize startup performance.
