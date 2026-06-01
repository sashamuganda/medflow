# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-06-01 - [Hardcoded PII in compiled Flutter JS]
**Vulnerability:** A hardcoded email address ('amara.okonkwo@gmail.com') was found within a password reset success message in the compiled 'main.dart.js' file.
**Learning:** Compiled assets can contain sensitive PII or secrets that may not be immediately obvious without searching the build output. This often happens due to hardcoded test data or mock values in the source code being included in the production build.
**Prevention:** Use environment variables or localization files for all user-facing strings and PII placeholders. Always scan compiled artifacts for sensitive patterns (emails, keys) before deployment.
