# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [CSP Meta Tag Consolidation]
**Vulnerability:** Redundant and inconsistent Content-Security-Policy and Referrer-Policy meta tags.
**Learning:** Browsers enforce the intersection of all CSP meta tags present in a document. A resource is only allowed if it passes ALL policies. Duplicate tags with mismatched directives often cause functional bugs that are hard to debug because it's not always obvious which policy is blocking a resource.
**Prevention:** Ensure exactly one CSP meta tag and one Referrer-Policy meta tag are present in `index.html`.
