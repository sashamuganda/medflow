# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-13 - [Hardening CSP with Trusted Types and duplicate tag removal]
**Vulnerability:** Duplicate CSP and Referrer-Policy tags causing ambiguous browser enforcement, and missing modern protections like Trusted Types and `object-src 'none'`.
**Learning:** Browsers enforce the *intersection* of multiple CSP tags, which can lead to subtle functional bugs or unintended security gaps if policies are not perfectly synchronized. Explicitly enabling Trusted Types in the CSP is required even if the application code creates the policy, to ensure the browser strictly enforces it.
**Prevention:** Consolidate security headers into single, robust declarations and utilize `require-trusted-types-for 'script'` for modern XSS defense in Flutter Web apps.
