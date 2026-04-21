## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2026-04-21 - Preloading Specific CanvasKit Variants
**Learning:** Flutter Web often uses a browser-optimized CanvasKit variant (e.g., in `canvaskit/chromium/`). Preloading the generic `canvaskit/canvaskit.wasm` might still lead to a late fetch if the engine decides to use the chromium-specific one.
**Action:** Identify the specific variant being fetched by the engine (using Playwright or DevTools) and preload that specific path to maximize performance gains.
