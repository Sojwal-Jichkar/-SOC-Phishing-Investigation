# Phishing Email Forensics — IOC Report
**Analyst:**Sojwal Jichkar  
**Date:** May 2026 
**Severity:** HIGH  

## Project Overview
Investigated a real phishing email 
impersonating DocuSign using free 
SOC tools.

## Tools Used
- MXToolbox — Email header analysis
- VirusTotal — URL and IP reputation  
- AbuseIPDB — IP abuse check

## Key Findings
- SPF, DKIM, DMARC — all FAILED
- Sending IP flagged 18 times globally
- 39% abuse confidence score
- Confirmed phishing — T1566.002

## Files in this Repository
- Email Investigation.txt
- sojwal_IOC_Report_Final.pdf
- Malicious analysis document.txt
-IOC Report.txt
## MITRE ATT&CK
- TA0001 Initial Access
- T1566.002 Spearphishing Link
