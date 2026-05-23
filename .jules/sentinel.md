# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-23 - [CSP Intersection and Meta-Tag Hygiene]
**Vulnerability:** Redundant and conflicting Content-Security-Policy meta tags.
**Learning:** CSP directives are additive; the browser enforces the most restrictive intersection of all policies. Redundant tags increase maintenance complexity and risk accidental breakage or security gaps if not merged correctly.
**Prevention:** Consolidate all security policies into single, unique meta tags and use defense-in-depth directives like 'object-src none'.
