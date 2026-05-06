# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-06 - [CSP Consolidation and Intersection]
**Vulnerability:** Redundant and inconsistent Content-Security-Policy meta tags.
**Learning:** Browsers enforce the intersection of all CSP meta tags in a document. A resource is only allowed if it passes *all* policies. Duplicated tags with different allowed origins often cause silent failures where one policy blocks what another intended to allow.
**Prevention:** Maintain exactly one consolidated CSP meta tag to ensure a single, predictable source of truth for resource loading permissions.
