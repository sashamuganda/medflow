# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-27 - [Trusted Types Enforcement for Flutter Web]
**Vulnerability:** XSS risk due to potentially unsafe script assignments or DOM sinks.
**Learning:** Flutter Web's `flutter_bootstrap.js` implements a `flutter-js` Trusted Types policy. Enforcing this via CSP (`require-trusted-types-for 'script'; trusted-types flutter-js;`) provides a strong layer of defense by ensuring only framework-vetted scripts are executed.
**Prevention:** Explicitly enable and enforce the framework-provided Trusted Types policy in the CSP.
