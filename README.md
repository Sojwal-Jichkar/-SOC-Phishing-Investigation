
# Phishing Email Forensics — SOC Investigation & IP Reputation Case Study

**Analyst:** Sojwal Jichkar
**Type:** Training Exercise / Portfolio Project
**Status:** Practice Investigation

## Project Overview

This project demonstrates the analytical process a SOC L1 analyst follows when investigating a phishing email — from header analysis through IOC extraction to MITRE ATT&CK mapping and recommended response.

**Note on data:** Part 1 below uses a constructed training scenario, not a captured real-world email. All values (sender domain, phishing URL, header data) are either invented or use documentation-reserved example ranges (RFC 5737), so this is disclosed upfront rather than presented as a live incident. Part 2 uses a real, verifiable public IP address and real OSINT tool results.

## Tools Used
- MXToolbox — Email header analysis
- VirusTotal — URL and IP reputation
- AbuseIPDB — IP abuse reporting and confidence scoring

## Part 1: Simulated Phishing Investigation
- Constructed a realistic phishing email impersonating DocuSign
- Performed email header analysis: SPF, DKIM, and DMARC all FAIL, consistent with a spoofed sender
- Extracted IOCs and mapped findings to MITRE ATT&CK
- Documented severity rationale and recommended response actions

Full write-up: `ioc-report-final.pdf`
Raw simulated header: `email-header-analysis.txt`

## Part 2: Real-World IP Reputation Case Study
- Investigated a real, publicly known IP address (185.199.108.153) on VirusTotal and AbuseIPDB
- Confirmed via HTTP response headers that this IP belongs to GitHub Pages' shared CDN infrastructure (operated by Fastly), not a dedicated attacker host
- **Key lesson:** abuse scores and detection counts on shared cloud/CDN IPs can be misleading. Blocking shared infrastructure based on reputation score alone can break access to thousands of unrelated legitimate services. Ownership/ASN must be verified before recommending an IP block.

Full write-up: included in `ioc-report-final.pdf`, Part 2

## MITRE ATT&CK Mapping
| Tactic | Technique | Why it applies |
| TA0001 Initial Access | T1566.002 Spearphishing Link | Email delivers a malicious link impersonating a trusted brand to steal credentials |
| TA0001 Initial Access | T1036.005 Match Legitimate Name or Location | Spoofed domain closely mimics the real DocuSign brand to deceive the recipient |

## Files in This Repository
- `README.md` — project overview (this file)
- `email-header-analysis.txt` — simulated raw email header used for the exercise
- `ioc-report-final.pdf` — full investigation report (Part 1 + Part 2)

## Skills Demonstrated
Email header analysis, SPF/DKIM/DMARC verification, IOC extraction and documentation, MITRE ATT&CK mapping, IP/domain reputation analysis, critical evaluation of threat intelligence data, structured incident reporting
