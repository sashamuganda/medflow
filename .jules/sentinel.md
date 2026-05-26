# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-26 - [CSP Hardening and Trusted Types Enforcement]
**Vulnerability:** Redundant and partially conflicting CSP meta tags; missing modern defenses like Trusted Types and `object-src 'none'`.
**Learning:** Browsers enforce the intersection of all CSP policies if multiple meta tags are present. Consolidating into a single policy ensures clarity and consistent enforcement. Flutter Web can be secured with Trusted Types by explicitly allowing the `flutter-js` policy in the CSP.
**Prevention:** Audit `index.html` for duplicate security headers and always enforce Trusted Types to mitigate DOM-XSS in script-heavy applications.
