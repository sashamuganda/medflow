# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-25 - [Duplicate Security Meta Tags]
**Vulnerability:** Redundant and potentially conflicting `Content-Security-Policy` and `Referrer-Policy` meta tags in `index.html`.
**Learning:** Browsers enforce multiple CSP policies by intersection, which can lead to unintended blocking if policies are inconsistent. Duplicate meta tags also increase document size and can lead to maintenance errors.
**Prevention:** Consolidate security policies into single, well-defined meta tags and use `grep` during audits to ensure no duplicates exist.
