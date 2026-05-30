# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-12 - [Hardening Flutter Web with Trusted Types]
**Vulnerability:** DOM-based XSS risks in complex web frameworks like Flutter.
**Learning:** Flutter Web's `flutter.js` (and `flutter_bootstrap.js`) implements a Trusted Types policy named `flutter-js`. Enforcing this via CSP (`require-trusted-types-for 'script'`) provides a powerful defense against XSS by restricting sinks like `innerHTML` and `script.src` to only accept objects created by authorized policies.
**Prevention:** Explicitly enable and enforce the `flutter-js` Trusted Types policy in the `index.html` CSP for all Flutter Web deployments.
