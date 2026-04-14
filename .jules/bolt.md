## 2026-04-14 - Standard Flutter Web Optimizations
**Learning:** Initial load performance for Flutter Web is heavily dependent on the order of resource fetching and the location of engine assets. Preloading `main.dart.js` with `fetchpriority="high"` ensures the main logic starts downloading immediately, while `useLocalCanvasKit: true` avoids external dependency on `gstatic.com`, reducing DNS and latency overhead.
**Action:** Always verify if these two optimizations are implemented when working on Flutter Web projects.
