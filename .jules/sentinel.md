# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-15 - [Trusted Types and CSP Consolidation]
**Vulnerability:** Duplicate and inconsistent security meta tags in `index.html`.
**Learning:** Browsers enforce the intersection of multiple CSPs, which can cause subtle functional bugs if they aren't identical. Consolidation ensures a predictable security posture. Modern Flutter Web engines implement their own Trusted Types policy (e.g., `flutter-js`), and explicitly requiring Trusted Types in the CSP (`require-trusted-types-for 'script'; trusted-types flutter-js;`) provides a strong defense against XSS.
**Prevention:** Periodically audit `index.html` for duplicate meta tags and always enable Trusted Types for applications that support them.
