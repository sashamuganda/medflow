# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-04 - [Security Header Consolidation and Hardening]
**Vulnerability:** Redundant and conflicting security meta tags (CSP and Referrer-Policy) in index.html.
**Learning:** Browsers enforce all CSPs present on a page, meaning a resource must satisfy the intersection of all policies. Conflicting duplicate tags can lead to unexpected resource blocking. Consolidating into a single, comprehensive policy ensures predictable enforcement.
**Prevention:** Maintain a single source of truth for security headers and periodically audit for duplicate or conflicting directives. Always include 'object-src 'none'' to mitigate plugin-based injection risks.
