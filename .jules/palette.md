# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2025-04-13 - Branding Consistency and Loading Accessibility
**Learning:** Inconsistent capitalization of the app name (e.g., 'medflow' vs 'Medflow') in metadata like `<title>` and `manifest.json` detracts from a professional feel. Additionally, the initial loading container should have `role="status"` and a descriptive `aria-label` to inform screen reader users.
**Action:** Always verify branding capitalization across all entry point metadata and ensure the loading state is accessible.
