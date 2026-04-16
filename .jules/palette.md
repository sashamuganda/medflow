## 2025-05-14 - Loading State for Flutter Web
**Learning:** Flutter web applications often display a blank screen while the engine and main script are loading. Providing a simple CSS-based loading indicator in the host HTML file significantly improves perceived performance and user experience.
**Action:** Always include a lightweight loading spinner and matching background color in `index.html` for Flutter Web projects, and use the `onEntrypointLoaded` callback to remove it.

## 2025-05-14 - Base Accessibility for Static Builds
**Learning:** Standard Flutter web builds often omit the `lang` attribute on the `<html>` tag, which is a basic accessibility requirement for screen readers.
**Action:** Ensure `lang="en"` (or the appropriate language code) is present in the `index.html` file.
