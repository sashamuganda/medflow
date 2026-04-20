# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-04-20 - [Redundant and Weak CSP Policy Consolidation]
**Vulnerability:** Redundant and inconsistent Content-Security-Policy and Referrer-Policy meta tags in `index.html`.
**Learning:** Build artifacts can sometimes accumulate duplicate security headers if multiple optimization steps or manual edits are applied without consolidation. Browsers enforce multiple CSPs by intersection, which can lead to unexpected breakage if policies conflict or are overly restrictive in one instance and permissive in another. Hardening the policy with `object-src 'none'`, `base-uri 'self'`, and `form-action 'self'` significantly reduces the attack surface for injection and hijacking.
**Prevention:** Regularly audit the final build artifacts to ensure security headers are consolidated, consistent, and follow the principle of least privilege.
