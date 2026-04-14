## 2026-04-14 - Securing Flutter Web static artifacts
**Vulnerability:** Defense-in-depth and supply chain risk. The application lacked security headers (CSP, Referrer-Policy) and was configured to potentially load CanvasKit from an external CDN (gstatic.com).
**Learning:** For static Flutter Web builds, security must be implemented via `<meta>` tags since there's no dynamic server to provide headers. Additionally, the Flutter engine's `useLocalCanvasKit` configuration in `flutter_bootstrap.js` is critical for ensuring self-contained and privacy-preserving execution.
**Prevention:** Always include a baseline CSP whitelisting only necessary domains (gstatic.com, fonts.gstatic.com, images.unsplash.com) and force local loading of engine dependencies when possible.
