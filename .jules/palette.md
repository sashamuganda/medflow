# Palette's Journal - Critical Learnings

## 2025-04-12 - Loading Feedback for Flutter Web
**Learning:** Users of Flutter Web often experience a "white screen" during initial engine load, which can be interpreted as a hang. A simple HTML/CSS spinner in index.html provides immediate feedback.
**Action:** Always include a lightweight loading indicator in index.html and hook into the Flutter loader lifecycle to remove it.

## 2025-04-12 - Accessibility Baseline for Flutter
**Learning:** Screen readers cannot identify the language of a Flutter Web app if the underlying HTML lacks the lang attribute, even if the app itself is localized.
**Action:** Ensure <html lang="en"> (or appropriate language) is set in the entry point.

## 2026-04-18 - Verifying Early Loading States
**Learning:** Standard Playwright `goto` waits for `load` or `networkidle`, which often skips the initial CSS-only loading state in fast local environments.
**Action:** Use `page.goto(url, wait_until='commit')` and `locator.wait_for(state='visible')` to reliably capture and verify early-stage loading UI.
