# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2025-05-14 - Ensuring Visibility of Initial Loading States
**Learning:** In the default Flutter Web artifacts of this repository, the `index.html` file includes the HTML for a loading indicator (`#loading` and `.loader`) but lacks the corresponding CSS in the `<head>`, meaning the loading state is effectively invisible until custom styles are implemented.
**Action:** Always provide explicit CSS for `#loading` and `.loader` in `index.html` and use `position: fixed` with a high `z-index` to ensure visibility during the early stages of engine initialization.
