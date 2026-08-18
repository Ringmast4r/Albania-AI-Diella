# EXPOSED DATA SUMMARY
## Albanian Government / AKSHI / Diella
### January 2026

---

## Status: DATA PREVIOUSLY EXPOSED (Not by us)

This research found that massive amounts of Albanian citizen PII and government data have already been exposed through:
1. Internal data breaches (2021)
2. Iranian state-sponsored cyberattacks (2022-2024)
3. Ongoing Telegram distribution

---

## Currently Accessible Leak Channels

### Telegram (ACTIVE)
| Channel | URL | Content |
|---------|-----|---------|
| @justice_homeland | https://t.me/justice_homeland | 13.6k members, leaked databases |
| @JusticeHomeland1 | https://t.me/JusticeHomeland1 | "Official" channel |

### Websites (ACTIVE)
| URL | Status |
|-----|--------|
| https://justicehomeland.ru | Active |
| https://justicehomeland.org | Active |

### Claimed Data Sources
- **E-Albania** - Main government services portal
- **TIMS** - Border/immigration tracking system
- **Memex** - Police suspect database
- **Deep Sea** - Unknown system
- **Credins Bank** - Banking data
- **AMC** - Albanian Mobile Communications

---

## Historical Data Breaches (Verified)

### April 2021 - Voter Database
| Field | Detail |
|-------|--------|
| Records | 910,000 |
| Population % | ~33% |
| Format | Microsoft Access |
| Data Types | Names, IDs, phones, voting centers, employers, political affiliations |
| Distribution | Leaked to media |

### December 2021 - Salary Database
| Field | Detail |
|-------|--------|
| Records | 637,138 |
| Population % | 22% |
| Format | Excel |
| Data Types | Names, ID numbers, salaries, job positions, employers |
| Distribution | WhatsApp |

### October 2022 - Police Suspect Database
| Field | Detail |
|-------|--------|
| Records | ~100,000 |
| File Size | 1.7 GB |
| Data Types | Photos, ID numbers, names, fathers' names, DOB, birthplace, nationality |
| Distribution | Telegram (@justice_homeland) |

### 2022 - Government Officials
- Police Chief: Personal info + border crossing records
- Interior Minister: Email mailbox
- Defense Minister: Email mailbox
- Prime Minister: Correspondence with citizens
- SHISH (Intelligence): Employee names, emails, phone numbers

### 2023-2024 - Infrastructure Attacks
- Parliament systems targeted
- One Albania (telecom) - claimed 2 petabytes deleted
- INSTAT - claimed 100TB exfiltrated
- Air Albania compromised

---

## Current OSINT Findings (Passive)

### Exposed Assets (No auth required)
| Asset | URL | Risk |
|-------|-----|------|
| Diella Frontend | proud-coast-026495803.4.azurestaticapps.net | Low - No sensitive data in JS |
| WordPress readme | akshi.gov.al/readme.html | Low - Version fingerprinting |
| 50+ subdomains | Via crt.sh | Info disclosure |

### Protected/Hardened
- WordPress REST API requires authentication
- WAF blocks sensitive file requests
- User enumeration disabled
- No gravatar hashes exposed
- No API keys in frontend JS bundle

---

## Key Intelligence

### AKSHI Compromise Timeline
```
May 2021    - Iranian hackers gain initial access
July 2022   - Destructive attack launched
Sept 2022   - Albania cuts ties with Iran
Dec 2025    - AKSHI leadership arrested for corruption
Jan 2026    - Diella still operational under compromised agency
```

### Attack Infrastructure
- Initial vector: CVE-2019-0604 (SharePoint)
- Persistence: ASPX web shells
- Malware: ROADSWEEP, ZeroCleare, CHIMNEYSWEEP
- Attribution: Iranian MOIS (confirmed by FBI, NATO, UK)

---

## Recommendations

### For Researchers
1. Monitor @justice_homeland Telegram for new leaks
2. Check justicehomeland.ru/.org for announcements
3. Monitor crt.sh for new AKSHI subdomains
4. Track Azure static app for API exposure

### Unanswered Questions
1. Is Diella's training data from compromised systems?
2. What data does Diella have access to?
3. Were AKSHI's corrupted officials involved with Diella?
4. Has the 2022 breach been fully remediated?

---

## Legal Note

All information in this report was gathered through passive OSINT:
- Public web searches
- Certificate transparency logs
- Publicly accessible URLs
- Published news reports

No systems were accessed, credentials tested, or vulnerabilities exploited.

---

*Compiled: January 25, 2026*
