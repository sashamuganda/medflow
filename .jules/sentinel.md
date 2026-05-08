# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-08 - [Duplicate Security Meta Tags]
Vulnerability: Duplicate `Content-Security-Policy` and `referrer` meta tags in `index.html`.
Learning: Browsers enforce the intersection of all CSP policies present. Duplicate tags with mismatched directives can cause functional bugs and are a maintenance burden.
Prevention: Ensure only one of each security meta tag is present and that it is consolidated and hardened (e.g., adding `object-src 'none'`).
