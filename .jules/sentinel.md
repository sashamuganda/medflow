# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-24 - [Trusted Types Enforcement for Flutter Web]
**Vulnerability:** Redundant and inconsistent Content-Security-Policy tags, and lack of explicit Trusted Types enforcement.
**Learning:** Flutter Web's initialization scripts (`flutter_bootstrap.js`) implement a Trusted Types policy named `flutter-js`. While the scripts use this policy, the browser does not enforce it unless the CSP includes `require-trusted-types-for 'script'` and `trusted-types flutter-js`.
**Prevention:** Always consolidate CSP tags and explicitly enable Trusted Types enforcement for Flutter Web projects to prevent DOM-based XSS.
