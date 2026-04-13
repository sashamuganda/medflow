## 2025-05-14 - Defense-in-Depth Security Enhancements
**Vulnerability:** Lack of Content Security Policy (CSP) and weak default Referrer Policy in a static Flutter Web build.
**Learning:** Flutter Web applications often rely on external CDNs (like gstatic.com) for CanvasKit and fonts, requiring a CSP that carefully balances security with framework needs (including `unsafe-eval` and `unsafe-inline`).
**Prevention:** Always implement a restrictive CSP and `strict-origin-when-cross-origin` referrer policy. Forcing local CanvasKit via `useLocalCanvasKit: true` in `_flutter.buildConfig` reduces the attack surface by eliminating third-party JS/WASM loads for the core engine.
