# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2025-05-14 - Loading Spinner Styling and Accessibility
**Learning:** When styling a loading spinner for a brand-colored background (e.g., #0175C2), using semi-transparent white (rgba(255, 255, 255, 0.2)) for the border and solid white for the rotating segment ensures high contrast and visibility. Adding descriptive aria-labels (e.g., "Loading Medflow...") in addition to role="status" ensures the state is properly announced by screen readers.
**Action:** Use brand-consistent colors and provide descriptive ARIA labels for loading states.
