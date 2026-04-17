# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-17 - [Consolidation of Redundant Security Meta Tags]
**Vulnerability:** Redundant and conflicting Content-Security-Policy and Referrer-Policy meta tags.
**Learning:** Browsers enforce the intersection of multiple CSP policies, meaning if any policy blocks a resource, it remains blocked even if another policy allows it. This can lead to functional breakages and unpredictable security posture. Additionally, 'frame-ancestors' is only supported via HTTP headers and ignored in meta tags.
**Prevention:** Maintain a single, consolidated CSP meta tag that represents the complete policy required for the application.
