# OSINT Report: Diella AI System (Albania)
## Research Date: January 25, 2026

---

## Executive Summary

**Diella** is Albania's AI-powered virtual assistant, developed by AKSHI (National Agency for Information Society) using Microsoft Azure and OpenAI technology. In September 2025, it became the world's first AI system formally appointed to a cabinet-level government position as "Minister of State for Artificial Intelligence."

---

## 1. Infrastructure Analysis

### Primary Domains

| Domain | IP Address | ASN | Location |
|--------|-----------|-----|----------|
| e-albania.al | 134.0.39.39 | AS5576 AKSHI | Tirana, Albania |
| akshi.gov.al | 134.0.42.170 | AS5576 AKSHI | Tirana, Albania |

### Hosting

- **ASN**: AS5576 - Agjencia Kombetare Shoqerise se Informacionit
- **Location**: Tirana, Albania (41.3274, 19.8187)
- All infrastructure appears to be self-hosted within Albanian government data centers

### Azure Integration

- Azure Static Apps endpoint discovered: `proud-coast-026495803.4.azurestaticapps.net`
- Application Insights instrumentation key: `40a2cf63-ce16-4617-afe4-c618d01198ef`

---

## 2. Technology Stack

### e-Albania Platform

| Component | Technology |
|-----------|------------|
| Backend | ASP.NET |
| Frontend | jQuery, Bootstrap, SweetAlert2 |
| Cloud | Microsoft Azure (Static Apps, Application Insights) |
| Analytics | Google Analytics (UA-122218565-1) |
| AI/LLM | OpenAI via Azure |

### AKSHI Website

| Component | Technology |
|-----------|------------|
| CMS | WordPress |
| Server | nginx/1.19.10 |
| API | WordPress REST API (wp-json) |

---

## 3. Discovered API Endpoints (e-Albania)

```
/GGInteractions.aspx/TokenRefresh
/GGInteractions.aspx/GetBootstrapToken
/DBServices.aspx/GetServiceList
/DBServices.aspx/CanUserRateService
/DBServices.aspx/RateService
/Handlers/PostBloodGroupConsent.ashx
/Authenticate.aspx
```

---

## 4. AKSHI Subdomains (from crt.sh)

### Core Services
| Subdomain | Purpose |
|-----------|---------|
| e-albania.al | Main citizen services portal |
| akshi.gov.al | Agency main website |
| eauth.akshi.gov.al | Authentication services |
| esign.akshi.gov.al | Electronic signatures |
| eform.akshi.gov.al | Electronic forms |

### Development/Internal Infrastructure
| Subdomain | Technology/Purpose |
|-----------|-------------------|
| dc.akshi.gov.al | Data center |
| dc-hasura.akshi.gov.al | Hasura GraphQL engine |
| dc-keycloak.akshi.gov.al | Keycloak authentication |
| dc-rest.akshi.gov.al | REST API services |
| dc-serve.akshi.gov.al | Service endpoint |
| cloud.akshi.gov.al | Cloud services |
| code-server.akshi.gov.al | VS Code server (development) |
| collabora.akshi.gov.al | Collabora Online (document editing) |

### Other Subdomains
- abi.akshi.gov.al
- ams.akshi.gov.al
- bsurvey.akshi.gov.al
- cwp.akshi.gov.al / cwp2 / cwp7
- dcim.akshi.gov.al
- dergo.akshi.gov.al
- mona.akshi.gov.al
- punaime.akshi.gov.al
- research.akshi.gov.al
- sherbime.akshi.gov.al
- tm.akshi.gov.al
- trajnime.akshi.gov.al

---

## 5. Diella AI System Details

### Identity
- **Name**: Diella (from Albanian "diell" = sun)
- **Appearance**: Female avatar in traditional Zadrimë costume
- **Voice**: Albanian actress Anila Bisha (contract through Dec 2025)
- **Role**: Minister of State for Artificial Intelligence

### Version History
| Version | Date | Capabilities |
|---------|------|--------------|
| Diella 1.0 | January 2025 | Text-based chatbot on eAlbania |
| Diella 2.0 | Mid-2025 | Voice interaction, animated avatar |
| Cabinet Role | September 2025 | Formal ministerial appointment |

### Technical Architecture
- **Developer**: AKSHI Artificial Intelligence Laboratory
- **LLM Provider**: OpenAI (via Microsoft Azure)
- **Hosting**: Microsoft Azure
- **Integration**: eAlbania platform
- **Workflows**: Custom scripts by Albanian developers

### Capabilities (as of mid-2025)
- Access to 36,000+ government documents
- Integration with ~1,000 public services
- Voice-based ID renewal applications
- Real-time citizen guidance

### Future Plans (2026)
- 83 AI "children" (parliamentary assistants)
- AI monitoring of legislative sessions
- Expanded procurement oversight

---

## 6. AKSHI Organization Profile

### Full Name
Agjencia Kombëtare e Shoqërisë së Informacionit
(National Agency for Information Society)

### Key Infrastructure
| System | Description |
|--------|-------------|
| GOVnet | Secure network connecting 220 institutions |
| DataCenter | Hosts 380 government websites |
| e-Albania | 600+ electronic services |
| Interoperability Platform | Connects 30 state systems |
| CSIRT | Government cybersecurity operations |
| PKI | Digital signature services |

### Achievements
- Ranked 14th globally in GovTech Maturity Index 2025
- UN recognition as model for digital transformation

---

## 7. Security Observations

### Positive
- HSTS enabled on main domains
- Self-hosted infrastructure (data sovereignty)
- Keycloak for authentication (modern IAM)

### Points of Interest
- WordPress REST API active on akshi.gov.al (users endpoint returned empty/blocked)
- Multiple cPanel/webmail subdomains exposed in certificate transparency
- Development infrastructure visible (code-server, collabora)

### No Public Vulnerabilities Found
- User enumeration blocked on WordPress
- API endpoints require authentication
- WordPress posts endpoint also requires auth (unusual, extra hardened)

### Government Site Security

| Domain | Status |
|--------|--------|
| akshi.gov.al | WP API locked (401) |
| kryeministria.al | Incapsula WAF |
| president.al | Cloudflare protected |
| parlament.al | React SPA (no WP) |
| e-albania.al | ASP.NET (no WP) |

**Conclusion:** No exposed gravatar hashes. Albanian government infrastructure is well-secured.

---

## 8. Sources

- [Wikipedia - Diella (AI system)](https://en.wikipedia.org/wiki/Diella_(AI_system))
- [TIME - Albania's AI-Powered Minister](https://time.com/7324934/albania-ai-minister-diella/)
- [Al Jazeera - Albania appoints AI bot minister](https://www.aljazeera.com/news/2025/9/12/albania-appoints-ai-bot-minister-to-fight-corruption-in-world-first)
- [Balkan Insight - Albania's AI Minister](https://balkaninsight.com/2025/09/16/albanias-headline-grabbing-ai-minister-is-a-risky-innovation/)
- [EU ISS - AI Minister and EU Accession](https://www.iss.europa.eu/publications/commentary/artificial-intelligence-real-politics-what-albanias-ai-minister-means-eu)
- [Lowy Institute - AI Minister Analysis](https://www.lowyinstitute.org/the-interpreter/albania-s-ai-generated-minister-impressive-spectacle-questionable-reform)
- [Wikipedia - eAlbania](https://en.wikipedia.org/wiki/EAlbania)

---

## 9. Conclusion

Diella represents a novel experiment in AI governance. The system is built on established enterprise technology (Azure/OpenAI) but controlled by Albania's government IT agency. While marketed as an anti-corruption tool for public procurement, analysts note it remains "more symbol than substance" at this stage. The infrastructure is professionally managed with modern security practices, though development/internal subdomains are visible through certificate transparency.

---

*Report generated via OSINT research - January 2026*
