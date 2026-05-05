# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-05 - [Consolidated Security Policies]
**Vulnerability:** Duplicate and inconsistent CSP/Referrer-Policy meta tags in index.html.
**Learning:** Browsers may enforce the intersection of multiple CSPs, which can lead to unexpected resource blocking if tags are inconsistent. Redundant tags also increase the attack surface and configuration complexity.
**Prevention:** Ensure exactly one Content-Security-Policy and one Referrer-Policy meta tag exist in the HTML head. Consolidate all required origins into the single CSP and include defense-in-depth directives like `object-src 'none'`.
