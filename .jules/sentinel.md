# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-13 - [CSP Meta Tag Intersection]
**Vulnerability:** Redundant and conflicting Content-Security-Policy meta tags.
**Learning:** Browsers enforce the intersection of all CSP policies present in a document. A resource is only allowed if it passes ALL policies. Having duplicate tags with different allowed origins can lead to functional breakages (e.g., blocking assets allowed in one tag but missing in another).
**Prevention:** Maintain a single, consolidated CSP meta tag to ensure predictable behavior and easier maintenance.
