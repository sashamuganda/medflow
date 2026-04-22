# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2026-04-22 - Invisible Loading Indicators
**Learning:** Compiled Flutter Web artifacts may include HTML elements for loading (e.g., #loading) but omit the CSS in the <head>. This results in a functional but invisible loading state that still delays the first meaningful paint.
**Action:** Verify that any pre-existing loading elements in index.html have corresponding CSS styles and accessibility roles.
