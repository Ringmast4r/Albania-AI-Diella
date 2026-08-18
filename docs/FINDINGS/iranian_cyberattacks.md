# HomeLand Justice: Iranian Cyberattacks on Albania
## Massive Data Leaks (2022-2024)

---

## Executive Summary

Iranian state-sponsored hackers operating under the name **"HomeLand Justice"** conducted devastating cyberattacks against Albanian government systems from 2022-2024, leaking massive amounts of citizen PII, government documents, and classified data via Telegram.

---

## Attack Timeline

| Date | Event |
|------|-------|
| May 2021 | Initial access gained (14 months before destructive attack) |
| July 18, 2022 | Albania forces temporary shutdown of government services |
| July 21, 2022 | HomeLand Justice claims responsibility, starts leaking data |
| September 7, 2022 | Albania severs diplomatic ties with Iran |
| September 19, 2022 | Police chief's personal data + border crossings leaked |
| October 3, 2022 | 300 criminal suspect identities leaked (1.7GB file) |
| December 2023 | Parliament + One Albania telecom attacked |
| December 24, 2023 | #DestroyDurresMilitaryCamp campaign begins |
| January 2024 | INSTAT (statistics institute) breached - 100TB claimed |

---

## Data Leaked via Telegram

### 1. Police Suspect Database
- **Records:** ~100,000 items
- **File Size:** 1.7 GB
- **Contents:**
  - Photographs
  - National ID numbers
  - Full names and fathers' names
  - Dates of birth
  - Birth cities
  - Nationality
- **Source:** Allegedly from MEMEX police system

### 2. Government Officials
- **Police Chief:** 47-page document with:
  - Personal identifying information
  - Border crossing records
- **Ministers:** Email mailboxes of:
  - Interior Minister Bledi Çuçi
  - Defense Minister Niko Peleshi
- **Prime Minister Rama:** Correspondence with citizens leaked

### 3. State Information Service (SHISH)
- Employee names and surnames
- Email addresses
- Mobile phone numbers
- **Implication:** Albania's intelligence agency compromised

### 4. Citizen Phone Numbers
- Mass leak of Albanian citizens' personal data:
  - Name, surname
  - Birthplace
  - Phone number
  - ID card number

### 5. Census/Statistics Data (2024)
- **Claimed:** 100+ Terabytes from INSTAT
- GIS data
- Census records

---

## Technical Analysis (MITRE ATT&CK)

**Campaign ID:** C0038

### Initial Access
- Exploited **CVE-2019-0604** (Microsoft SharePoint vulnerability)

### Malware Used
| Name | Type | Purpose |
|------|------|---------|
| ROADSWEEP | Ransomware | File encryption |
| ZeroCleare | Wiper | Disk destruction |
| CHIMNEYSWEEP | Infostealer | Data exfiltration |
| No-Justice | Wiper | 2024 attacks |

### Tools
- Mimikatz (credential dumping)
- Impacket (post-exploitation)
- RawDisk (disk access)
- ASPX web shells

### Persistence
- Web shells: `pickers.aspx`, `error4.aspx`, `ClientBin.aspx`
- Compromised administrator accounts

### Data Exfiltration
- HTTP POST requests from Exchange servers
- PowerShell mailbox searches
- Direct transfer to attacker infrastructure

---

## Distribution Channels (STILL ACTIVE)

### Websites
| URL | Status |
|-----|--------|
| homelandjustice.ru | Active (Russian domain) |
| justicehomeland.org | Active |

### Telegram Channels
| Handle | Members | Notes |
|--------|---------|-------|
| @justice_homeland | 13.6k | Primary data leak channel |
| @JusticeHomeland1 | Unknown | Claimed "official" channel |

**Contact:** @HomelandJustice (Telegram)

### Data Sources Mentioned on Channel
- E-Albania
- TIMS (border/immigration system)
- Memex (police database)
- Deep Sea
- Credins Bank databases
- AMC (Albanian Mobile Communications)

### Russian Connection
Contact details use Russian tech provider Yandex

---

## Attribution

### Confirmed by:
- FBI/CISA Joint Advisory (AA22-264A)
- Mandiant investigation
- Microsoft threat intelligence
- NATO official statement
- UK NCSC

### Associated Groups
- **HEXANE (G1001)** - Conducted reconnaissance
- Iranian Ministry of Intelligence and Security (MOIS)

### US Response
- Treasury Department sanctions on MOIS
- Sanctions on Iranian Intelligence Minister

---

## Targets

### Government
- AKSHI (National Agency for Information Society)
- Assembly of Albania (Parliament)
- State Police
- State Information Service (SHISH)
- INSTAT (Statistics Institute)

### Private Sector
- One Albania (telecom)
- Eagle Mobile Albania
- Air Albania

### Claims
- Deleted **2 petabytes** of telecom data (Dec 2023)
- Exfiltrated **100+ TB** of census data (Jan 2024)

---

## Motivation

**Retaliation for Albania hosting MEK**

The Mujahedeen-e-Khalq (People's Mojahedin Organization of Iran) maintains a refugee camp in Durrës, Albania. Iran considers MEK a terrorist organization and the attacks were explicit retaliation.

---

## Implications for Diella

1. **AKSHI Compromised:** The same agency that built Diella was directly attacked and compromised by Iranian hackers

2. **Data Integrity:** How can Diella's "36,000 government documents" be trusted if AKSHI's systems were breached?

3. **Trust Deficit:** Albanian citizens' data has been leaked multiple times - why would they trust an AI with access to more data?

4. **Security Questions:**
   - Was Diella's training data compromised?
   - Are the Azure/OpenAI integrations secure?
   - What data does Diella have access to?

---

## Sources

- [MITRE ATT&CK - HomeLand Justice (C0038)](https://attack.mitre.org/campaigns/C0038/)
- [CISA Advisory AA22-264A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-264a)
- [Balkan Insight - Criminal Suspects Leak](https://balkaninsight.com/2022/10/03/iranian-hackers-leak-database-of-albanian-criminal-suspects/)
- [Balkan Insight - War on Data](https://balkaninsight.com/2022/09/28/this-is-a-war-albania-struggles-to-keep-lid-on-hacked-data/)
- [Google Cloud - ROADSWEEP Analysis](https://cloud.google.com/blog/topics/threat-intelligence/likely-iranian-threat-actor-conducts-politically-motivated-disruptive-activity-against/)
- [Security Affairs - INSTAT Breach](https://securityaffairs.com/158555/hacking/iranian-hackers-hit-albania-instat.html)
- [The Hacker News - No-Justice Wiper](https://thehackernews.com/2024/01/pro-iranian-hacker-group-targeting.html)
- [CCDCOE Cyber Law Toolkit](https://cyberlaw.ccdcoe.org/wiki/Homeland_Justice_operations_against_Albania_(2022))

---

*Documented: January 2026*
