# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [Trusted Types Enforcement and CSP Consolidation]
**Vulnerability:** Potential DOM-based XSS and configuration confusion due to duplicate, weaker CSP meta tags.
**Learning:** Browsers enforce the intersection of all CSP policies present. Duplicate tags with mismatched directives can lead to functional breakage or accidental bypasses if developers assume only one is active. Flutter Web supports Trusted Types via the `flutter-js` policy, which must be explicitly allowed in the CSP when `require-trusted-types-for 'script'` is enabled.
**Prevention:** Maintain a single, consolidated CSP meta tag and enforce Trusted Types to systematically prevent DOM-XSS in Flutter Web applications.
