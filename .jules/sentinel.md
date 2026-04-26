# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-26 - [CSP Consolidation and Hardening]
**Vulnerability:** Redundant and potentially conflicting CSP and Referrer-Policy meta tags.
**Learning:** Browsers apply the intersection of multiple CSP meta tags, which can lead to overly restrictive policies or confusion. Consolidating into a single policy ensures clarity and allows for easier hardening with directives like `base-uri` and `form-action`.
**Prevention:** Maintain exactly one CSP and Referrer-Policy meta tag in `index.html`. Explicitly include `base-uri 'self'` and `form-action 'self'` to prevent base hijacking and unauthorized form submissions.
