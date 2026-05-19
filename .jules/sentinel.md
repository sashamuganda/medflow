# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-19 - [CSP Consolidation and Hardening]
**Vulnerability:** Duplicate and conflicting Content-Security-Policy meta tags in `index.html`.
**Learning:** Browsers enforce the intersection of all CSP policies when multiple meta tags are present. This can lead to silent failures where resources permitted by one tag are blocked by another.
**Prevention:** Consolidate security policies into a single, well-defined meta tag. Use `object-src 'none'` and `upgrade-insecure-requests` to further harden the policy.
