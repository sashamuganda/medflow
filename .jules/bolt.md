## 2025-04-16 - Preloading and Local Assets for Flutter Web
**Learning:** Preloading the `main.dart.js` bundle using `<link rel="preload">` and enabling `useLocalCanvasKit` in the Flutter loader significantly reduces the time-to-first-byte and script execution start for the application. In local profiling, `main.dart.js` load start moved from ~100ms to ~11ms.

**Action:** Implement preloading for the primary JS bundle and prefer local assets for the Flutter engine to minimize latency and external dependencies.

## 2025-04-16 - Artifact Cleanup
**Learning:** Temporary environment-specific hacks, like circular symbolic links used to satisfy base href routing in local servers, or log files from profiling scripts, must never be committed as they can cause infinite loops in build tools and clutter the repository.

**Action:** Explicitly include cleanup of all temporary files (symlinks, logs, profiling scripts) in the pre-commit checklist.
