## 2025-04-16 - Flutter Web CSP connect-src requirements
**Vulnerability:** Potential XSS or data exfiltration due to missing CSP.
**Learning:** In Flutter Web, fonts loaded from Google Fonts require `https://fonts.gstatic.com` to be explicitly allowed in the `connect-src` directive, not just `font-src`, because the Flutter engine fetches font bytes via the Fetch API.
**Prevention:** Always include `https://fonts.gstatic.com` in `connect-src` when allowing external fonts in Flutter Web.
