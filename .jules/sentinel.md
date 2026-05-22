# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-12 - [Redundant and conflicting security meta tags]
**Vulnerability:** Redundant `Content-Security-Policy` and `referrer` meta tags in `index.html`.
**Learning:** Browsers enforce the intersection (the most restrictive parts) of all active CSPs. Having duplicates makes the policy harder to audit and can lead to unexpected blocked resources if the policies diverge.
**Prevention:** Maintain a single, consolidated security policy in `index.html` to ensure clarity and auditability. Always include `object-src 'none'` to block plugins unless explicitly required.
