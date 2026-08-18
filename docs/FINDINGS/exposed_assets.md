# Exposed Assets - Albanian AI Infrastructure
## Date: January 25, 2026

---

## 1. AIBOT Azure Static App (Diella Frontend)

**URL:** `https://proud-coast-026495803.4.azurestaticapps.net`

**Status:** PUBLICLY ACCESSIBLE

**Description:** This appears to be the Diella AI chatbot frontend interface.

### Technical Details
```
Content-Type: text/html
Last-Modified: Mon, 15 Sep 2025 19:45:11 GMT (Diella appointment timeframe)
Platform: Azure Static Web Apps
Framework: Vue.js 3.5.13 (Quasar framework - #q-app div)
```

### HTML Source
```html
<meta name="description" content="AIBOT assistant">
<link rel="icon" type="image/png" sizes="32x32" href="/icons/favicon-32x32.png">
<script type="module" src="/assets/index.0c3452c3.js"></script>
<link rel="stylesheet" href="/assets/index.29d76a9b.css">
```

### Environment Variables Found (in JS bundle)
```
VUE_APP_STYLE_CHAT_MESSAGE_BOX_FONT_SIZE
VUE_APP_STYLE_CHAT_MESSAGE_BOX_FONT_WEIGHT
VUE_APP_STYLE_CHAT_MESSAGE_BOX_PADDING
VUE_APP_STYLE_FONT_FAMILY_NAME
VUE_APP_STYLE_INPUT_BG_COLOR
VUE_APP_STYLE_INPUT_BORDER_RADIUS
VUE_APP_STYLE_INPUT_COLOR
VUE_APP_STYLE_INPUT_DIFFERENT_BG_COLOR
VUE_APP_STYLE_INPUT_INNER_PADDING
VUE_APP_STYLE_INPUT_LABEL_COLOR
VUE_APP_STYLE_INPUT_PADDING_X
VUE_APP_STYLE_INPUT_PLACEHOLDER_OPACITY
VUE_APP_STYLE_RATING_ICONS_COLOR
```

### Assets
- `/assets/index.0c3452c3.js` (223KB minified JS)
- `/assets/index.29d76a9b.css`
- `/icons/favicon-32x32.png`
- `/icons/favicon-16x16.png`
- `/favicon.ico`

### Notes
- No hardcoded API keys found in JavaScript bundle
- API endpoints not visible (likely injected at runtime or proxied)
- Vue.js SPA with Quasar UI framework
- Last modified September 2025 (matches Diella cabinet appointment)

---

## 2. AKSHI WordPress Exposed Files

**Domain:** akshi.gov.al

### Accessible (but WAF protected)
| File | Status | Notes |
|------|--------|-------|
| /robots.txt | 200 | Disallow: / (blocks all crawlers) |
| /readme.html | 200 | WordPress readme (version info) |
| /license.txt | 200 | GPL license |
| /wp-login.php | 200 | Login page exists |

### WAF Blocked (returns error page)
| File | Status | Notes |
|------|--------|-------|
| /wp-config.php.bak | WAF BLOCK | "kod keqdashes" (malicious code) error |
| /.env | WAF BLOCK | Blocked as malicious |
| /xmlrpc.php | WAF BLOCK | Blocked as malicious |

### WordPress Info (from readme.html)
- PHP 7.2+ required
- MySQL 5.6+ required
- Standard WordPress installation

---

## 3. Development Subdomains (from crt.sh)

These subdomains exist in certificate transparency logs but are not publicly accessible:

| Subdomain | Technology | Status |
|-----------|------------|--------|
| code-server.akshi.gov.al | VS Code Server | No response |
| dc-hasura.akshi.gov.al | Hasura GraphQL | No response |
| dc-keycloak.akshi.gov.al | Keycloak IAM | No response |
| collabora.akshi.gov.al | Collabora Online | No response |
| dc.akshi.gov.al | Data Center | No response |

**Note:** These appear to be internal-only, not exposed to public internet.

---

## 4. Security Assessment

### What's Protected
- WordPress API requires authentication (401)
- WAF blocks suspicious file requests
- Sensitive files (.env, wp-config) blocked
- xmlrpc.php blocked
- User enumeration disabled

### What's Exposed
- AIBOT frontend on Azure (public)
- WordPress readme.html (version fingerprinting possible)
- robots.txt reveals they want to hide from crawlers
- Development subdomain names visible in CT logs

### Vulnerabilities
**None critical found.**

Minor information disclosure:
- Azure app naming convention reveals it's an "AIBOT assistant"
- WordPress version potentially identifiable via readme.html
- Subdomain enumeration possible via crt.sh

---

## 5. Recommendations for Further Research

1. Monitor the Azure static app for API endpoint exposure
2. Check if AIBOT requires authentication or is publicly usable
3. Research the Application Insights instrumentation key for data leakage
4. Monitor for new subdomain certificates

---

*Report generated via OSINT - January 2026*
