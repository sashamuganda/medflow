# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [Duplicate CSP Meta Tag Intersection]
**Vulnerability:** Duplicate Content-Security-Policy meta tags with mismatched directives causing functional breakage and configuration drift.
**Learning:** Browsers enforce the intersection of ALL CSP policies present in a document. If one tag allows a source but another doesn't, the resource is blocked. This can lead to subtle bugs where external assets (like Google Fonts or Unsplash images) fail to load even if they appear in one of the CSP tags.
**Prevention:** Maintain exactly one CSP meta tag to ensure a single source of truth and predictable browser enforcement.
