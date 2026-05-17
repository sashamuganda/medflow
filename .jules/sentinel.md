# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-14 - [Consolidation of Security Headers]
**Vulnerability:** Duplicate CSP and Referrer-Policy meta tags leading to configuration redundancy and potential functional breakage due to CSP intersection rules.
**Learning:** Browsers enforce the intersection of all CSP policies defined in meta tags. If multiple tags exist, a resource must pass ALL of them. Duplication often leads to one policy being updated while the other remains stale, causing "mismatched directives" bugs.
**Prevention:** Maintain a single, consolidated source of truth for security headers in the HTML head and use linting or automated checks to detect duplicate meta tags.
