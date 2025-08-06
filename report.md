# Report: Phishing Email Analysis
## Source:
- Phishing email sample downloaded from malware-traffic-analysis.net (2024-08-29)
- Filename: 2024-08-29-phishing-email-0415-UTC.eml

## Introduction:
Phishing remains one of the most common and dangerous cybersecurity threats. In this task, a real-world phishing email was analyzed to identify various signs of fraud, social engineering techniques, and technical inconsistencies that signal malicious intent.

## Objective:
The primary objective of this task was to critically examine a phishing email sample, dissect its technical components, identify the indicators of compromise, and summarize the key phishing traits to raise awareness and strengthen email threat detection skills.

### Email Overview:
- From: SupportDesk <khz.port@scp.gov.iq>
- To: admin@malware-traffic-analysis.net
- Subject: Account Validation!! For admin@malware-traffic-analysis.net Only!!
- Date: 28 August 2024
- Return-Path: <khz.port@scp.gov.iq>
- Message-ID: 20240828030626.DFAECAD6A3F54472@scp.gov.iq

### Technical Header Analysis:
- SPF (Sender Policy Framework): Fail  
  The sending IP address was not authorized to send mail on behalf of the scp.gov.iq domain.
- DKIM (DomainKeys Identified Mail): None  
  No DKIM signature was found in the message header, meaning the message integrity cannot be verified.
- DMARC (Domain-based Message Authentication, Reporting & Conformance): Fail  
  The domain did not pass either SPF or DKIM, and thus failed DMARC checks. This strongly indicates spoofing.
- Sending IP: 188.127.247.252  
  Reverse lookup shows this is not associated with any legitimate mail service for the claimed domain.
- Mail Servers (Received Headers):  
  The email passed through two unrelated servers, with an internal IP also appearing in the header trail — a common sign of relaying through compromised infrastructure.

### Email Body Analysis:
The body is formatted in HTML with elements designed to resemble an official notification. Key sections include:
- A message telling the recipient to “re-authenticate your account”
- A green “Re-authenticate Now” button that links to:  
  https://email.procedure.best/management.aspx?good=admin@malware-traffic-analysis.net
- A footer claiming confidentiality to build credibility
- A direct request for the user’s email password

##### The formatting is poor, with equal signs (=) and encoding artifacts like "3D" visible in the HTML, suggesting sloppy construction or intentional obfuscation.

#### Role of SPF, DKIM, and DMARC in Email Security:
SPF, DKIM, and DMARC are email authentication technologies that help identify forged sender addresses:
- SPF ensures the email comes from an IP allowed by the domain’s DNS.
- DKIM ensures the message was not altered in transit and was signed by the domain.
- DMARC combines SPF and DKIM to enforce policy and report fraud attempts.

##### In this case, the email fails all three, confirming it was sent from an unauthorized and suspicious source.

### Threat Assessment:
This phishing email is a classic example of a credential harvesting attempt. If the victim clicks the link and submits their email credentials, the attacker could:
- Compromise their email account
- Launch further phishing or malware attacks
- Access internal systems or data
- Attempt lateral movement within the organization

##### This could lead to data theft, financial loss, or widespread compromise.

### Key Phishing Indicators Identified:
1. Spoofed sender using .gov.iq domain unrelated to the recipient
2. Failed SPF, DKIM, and DMARC checks
3. Suspicious external URL not associated with any legitimate service
4. Direct request for sensitive credentials (email password)
5. Urgent and manipulative language (“please re-authenticate”)
6. Poor formatting and hidden encoded content in the HTML body
7. Message ID and sending IP not matching the organization


## Conclusion:
This phishing email is a targeted attack that uses impersonation, urgency, and visual tricks to deceive recipients into revealing their credentials. Through detailed analysis of both the headers and content, this report demonstrates how phishing attempts can be identified before damage occurs. Users must stay vigilant, and organizations should enforce strong email authentication policies.
