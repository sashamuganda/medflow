## 2026-04-12 - Optimizing Flutter Web Initial Load
**Learning:** Flutter Web by default may fetch CanvasKit from a CDN (gstatic.com), which adds DNS and connection overhead. Also, the large `main.dart.js` is often discovered late by the browser.
**Action:** Use `useLocalCanvasKit: true` in `_flutter.buildConfig` to force local assets, and use `<link rel="preload">` with `fetchpriority="high"` for critical JS assets.

## 2025-05-15 - Preloading CanvasKit and Inline Loading UI
**Learning:** For Flutter Web applications, the browser discovery of critical assets like 'canvaskit.wasm' and 'main.dart.js' can be delayed by several hundred milliseconds if left to the standard loader script. Additionally, a lack of inline CSS for the initial loading div results in a poor "white flash" experience.
**Action:** Always implement <link rel="preload"> with fetchpriority="high" for the specific CanvasKit variant used (e.g., 'canvaskit/chromium/canvaskit.wasm') and 'main.dart.js'. Ensure the initial loading indicator has inline CSS in the <head> to provide immediate, themed visual feedback.
