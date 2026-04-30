# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [CSP Consolidation and Hardening]
**Vulnerability:** Redundant and conflicting Content-Security-Policy meta tags in `index.html`.
**Learning:** Browsers enforce multiple CSPs by intersection, meaning a resource must satisfy ALL policies. Redundant tags can lead to accidental breakage if one policy is more restrictive than intended, or false security if one is loose. Hardening with `object-src 'none'`, `base-uri 'self'`, and `form-action 'self'` provides essential defense-in-depth.
**Prevention:** Ensure exactly one consolidated CSP meta tag exists, containing the union of all required origins and strict defensive directives.
