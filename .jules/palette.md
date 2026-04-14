## 2025-05-14 - Loading Spinner for Flutter Web
**Learning:** Adding a loading spinner in index.html and removing it via the 'onEntrypointLoaded' callback in flutter_bootstrap.js is a standard and effective UX improvement for Flutter Web projects to avoid the "blank screen" during engine initialization.
**Action:** Always check for existing loading indicators in Flutter Web projects and implement one if missing. Ensure removal logic happens after appRunner.runApp().
