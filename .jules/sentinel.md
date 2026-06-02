# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-06-02 - [PII exposure in build artifacts]
**Vulnerability:** Personal Identifiable Information (PII) such as personal email addresses can be leaked from the original source code into minified build artifacts like `main.dart.js`.
**Learning:** Build processes for Flutter Web do not automatically scrub hardcoded string literals used for testing or demo purposes. Manual remediation in the build bundle is sometimes necessary when source code is unavailable, but must be done carefully to avoid breaking functional, non-PII addresses (e.g., support emails).
**Prevention:** Use environment variables for all PII and sensitive strings during development to ensure they are never compiled into the production bundle.
