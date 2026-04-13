# Palette's UX Journal

## 2025-05-14 - Flutter Web Loading Performance
**Learning:** Flutter Web applications often suffer from a "white screen of death" during the several seconds it takes to download 'main.dart.js' and initialize the engine. This significantly degrades the first-load experience.
**Action:** Always implement a native HTML/CSS loading spinner in 'index.html' that is removed via the 'onEntrypointLoaded' callback in 'flutter_bootstrap.js'. This provides immediate feedback and reduces perceived latency.
