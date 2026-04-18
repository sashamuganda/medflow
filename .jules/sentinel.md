# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-18 - [Deduplication and Hardening of CSP and Referrer-Policy]
**Vulnerability:** Redundant and conflicting security meta tags in `index.html`.
**Learning:** Browsers enforce the intersection of multiple CSPs. If one policy blocks a source that another allows, the resource will be blocked. Consolidating into a single policy ensures clarity and correct enforcement. Adding `base-uri 'self'` and `form-action 'self'` provides additional protection against base URL hijacking and unauthorized form submissions.
**Prevention:** Regularly audit `index.html` for duplicate meta tags and ensure CSPs are consolidated and hardened with directives like `base-uri` and `form-action`.
