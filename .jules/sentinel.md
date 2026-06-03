# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [Trusted Types enforcement in Flutter Web]
**Vulnerability:** Potential for DOM-based XSS despite having a CSP, if Trusted Types are not enforced.
**Learning:** Flutter Web engine implements its own Trusted Types policy named `flutter-js`. Enforcing Trusted Types via CSP (`require-trusted-types-for 'script'; trusted-types flutter-js;`) provides a strong layer of defense against DOM-based XSS by restricting dangerous sinks.
**Prevention:** In Flutter Web projects, always include `require-trusted-types-for 'script'` and authorize the `flutter-js` policy in the CSP.
