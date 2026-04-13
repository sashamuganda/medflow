## 2026-04-13 - Flutter Web Initial Load Optimization
**Learning:** Preloading `main.dart.js` with `fetchpriority="high"` significantly improves the initial load performance by starting the download as early as possible. In this specific codebase, using `useLocalCanvasKit: true` in `_flutter.buildConfig` informs the custom loader to use the local `canvaskit/` directory, avoiding external DNS lookups.
**Action:** Always consider preloading critical assets and leveraging local dependencies for compiled Flutter Web artifacts to improve load reliability and speed.
