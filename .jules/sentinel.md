# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-12 - [Redundant Security Header Consolidation]
Vulnerability: Redundant and conflicting Content-Security-Policy and Referrer-Policy meta tags in index.html.
Learning: Browsers enforce multiple CSPs by intersection, meaning a resource must satisfy ALL policies to be loaded. This can lead to unexpected breakage if tags are not perfectly synchronized. Consolidation into a single, comprehensive policy ensures predictable and correct enforcement.
Prevention: Audit build artifacts for duplicate security headers or meta tags and consolidate them into a single, unionized policy.
