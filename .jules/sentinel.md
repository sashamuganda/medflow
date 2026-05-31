# Sentinel's Journal

## 2026-04-12 - [CSP and Referrer-Policy implementation]
**Vulnerability:** Lack of defense-in-depth security headers in the initial Flutter Web build.
**Learning:** Flutter Web applications often require `'unsafe-inline'` and `'unsafe-eval'` in their CSP to function correctly due to how they initialize and manage the engine. Additionally, correctly naming the referrer meta tag as `name="referrer"` is critical for browser support.
**Prevention:** Always include a robust CSP and a privacy-preserving Referrer-Policy in the base HTML of web projects.

## 2026-05-31 - [Manual patching of compiled assets]
**Vulnerability:** Hardcoded PII (email address) in `main.dart.js`.
**Learning:** In repositories containing only build artifacts (like this Flutter Web output), security fixes for strings must sometimes be applied directly to minified JS files if source code is unavailable. However, these changes are brittle and will be lost if the project is rebuilt from source.
**Prevention:** Hardcoded sensitive data should be addressed in the original source code or via environment-based configuration during the build process.
