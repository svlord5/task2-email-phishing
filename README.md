#  Phishing Email Analysis - Task 2 (Cyber Security Internship)
##  Source
Phishing email sample from [malware-traffic-analysis.net (2024-08-29)](https://www.malware-traffic-analysis.net/2024/08/29/index.html)  
File analyzed: `2024-08-29-phishing-email-0415-UTC.eml`


##  Email Overview
- **From:** SupportDesk <khz.port@scp.gov.iq>
- **To:** admin@malware-traffic-analysis.net
- **Subject:** Account Validation!! For admin@malware-traffic-analysis.net Only!!
- **Date:** 28 Aug 2024
- **Return-Path:** <khz.port@scp.gov.iq>
- **Message-ID:** <20240828030626.DFAECAD6A3F54472@scp.gov.iq>

## Phishing Indicators

#### 1.  Spoofed Sender
- Sender uses a `.gov.iq` domain, which is unrelated to the recipient.
- Likely impersonating a trustworthy domain to trick users.

#### 2.  SPF, DKIM, and DMARC Failures
- SPF: **Fail**
- DKIM: **None**
- DMARC: **Fail**
- Indicates unauthorized server attempted to send the email.

#### 3.  Suspicious URL
- Link: `https://email.procedure.best/management.aspx?good=admin@malware-traffic-analysis.net`
- Not affiliated with the legitimate domain.
- Likely a phishing page designed to steal login credentials.

#### 4.  Urgent Language and Social Engineering
- Encourages immediate action: “Please re-authenticate your account.”
- Requests sensitive info: "Kindly input your email password"
- Creates a false sense of authority and urgency.

#### 5. Grammar and Formatting Issues
- Subject uses double exclamation marks (!!)
- Phrases like "Kindly input your email password" are unusual and overly formal.
- HTML formatting reveals sloppy construction (e.g., unescaped `=` symbols).

## Tools Used
- Linux terminal commands: `cat`, `grep`, `less`
- Manual header inspection
- [VirusTotal](https://www.virustotal.com/) for URL analysis (optional)
- Sample source: [Malware-Traffic-Analysis.net](https://www.malware-traffic-analysis.net)

## Summary of Phishing Traits
- Spoofed sender domain and email address
- Authentication failures (SPF, DKIM, DMARC)
- Mismatched and suspicious URLs
- Attempts to steal credentials via social engineering
- Poor formatting and grammar

## Key Concepts Covered
- Phishing
- Email spoofing
- Header analysis
- Social engineering
- Threat detection
