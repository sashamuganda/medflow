## 2025-04-15 - Optimizing Flutter Web Initial Load
**Learning:** For static Flutter Web builds, initial load performance is significantly impacted by the sequential loading of `flutter_bootstrap.js` -> `main.dart.js` -> `canvaskit.wasm`. Preloading `main.dart.js` and serving CanvasKit locally reduces TTI by starting downloads earlier and eliminating external DNS lookups.
**Action:** Always check if critical JS assets are preloaded and if large WASM dependencies like CanvasKit can be served from the same origin to reduce latency.
