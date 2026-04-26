# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2026-04-26 - Immediate Feedback for Flutter Web Initialization
**Learning:** In Flutter Web builds, there is a significant delay between the initial HTML load and the engine initialization. Without inline CSS in `index.html`, users see a blank screen or unstyled content even if a loading div exists.
**Action:** Always provide inline CSS for loading indicators and brand-colored backgrounds in `index.html` to ensure immediate, accessible feedback.
