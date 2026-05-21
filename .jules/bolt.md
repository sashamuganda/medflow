## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-05-21 - Preloading CanvasKit WASM
**Learning:** The CanvasKit binary (canvaskit.wasm) is often the largest asset and is discovered late by the Flutter engine. Preloading it with `<link rel="preload" as="fetch" crossorigin="anonymous">` allows the browser to fetch it in parallel with the main JS bundle.
**Action:** Always preload `canvaskit/chromium/canvaskit.wasm` when `useLocalCanvasKit` is enabled, ensuring correct attributes to match the engine's fetch request.
