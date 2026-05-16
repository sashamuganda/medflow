# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2024-05-16 - [CSP Meta Tag Consolidation and Trusted Types]
**Vulnerability:** Duplicate security meta tags and lack of Trusted Types enforcement.
**Learning:** Browsers enforce the *intersection* of all CSP meta tags present in a document. If multiple tags exist, a resource is only allowed if it satisfies every single policy, which often leads to functional breakages or "security theater" where one tag is bypassed but the other is not. Additionally, enforcing Trusted Types requires specific policy names (e.g., `flutter-js`) to be allow-listed in the CSP to support Flutter's dynamic script loading.
**Prevention:** Maintain a single, consolidated CSP meta tag to ensure predictable security behavior and explicitly white-list Trusted Types policies required by the framework.
