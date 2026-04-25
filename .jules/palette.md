# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2026-04-25 - Accessible Initial Loading for Flutter Web
**Learning:** For Flutter Web apps, providing an accessible and branded initial loading state in index.html is critical for both UX and screen reader compatibility. A bare "white screen" or a non-semantic spinner leaves users and assistive technology in the dark during the long JS engine load.
**Action:** Use role="status" and a clear aria-label on the loading container, and style it with brand colors and a CSS-only spinner in index.html to ensure it's visible even before the first script executes.
