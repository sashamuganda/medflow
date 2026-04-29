# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-29 - [CSP Consolidation and Hardening]
**Vulnerability:** Redundant and conflicting `Content-Security-Policy` and `Referrer-Policy` meta tags in `index.html`, leading to a brittle security posture and potential resource blocking via policy intersection.
**Learning:** Browsers enforce the intersection of all present CSP policies. Multiple tags can accidentally block resources that are permitted in one but omitted in another. Hardening a Flutter Web CSP requires balancing safety with engine requirements like `'unsafe-eval'` and `'unsafe-inline'`.
**Prevention:** Maintain a single, authoritative CSP meta tag and include defense-in-depth directives like `object-src 'none'`, `base-uri 'self'`, and `form-action 'self'` to prevent plugin execution and URL hijacking.
