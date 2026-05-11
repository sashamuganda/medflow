# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-12 - [CSP Hardening and Trusted Types Enforcement]
**Vulnerability:** Redundant and slightly conflicting CSP meta tags, and lack of Trusted Types enforcement.
**Learning:** Modern Flutter Web builds implement a Trusted Types policy named `flutter-js`. Enforcing Trusted Types via CSP (`require-trusted-types-for 'script'; trusted-types flutter-js;`) provides a strong layer of defense against DOM-XSS. Browsers enforce the intersection of all CSP policies, so multiple `<meta>` tags should be avoided to prevent configuration bugs and ambiguity.
**Prevention:** Consolidate security headers into a single source of truth and enable modern browser security features like Trusted Types whenever supported by the framework.
