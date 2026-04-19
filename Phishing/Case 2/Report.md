# Phishing Email Analysis Report – TBFC-IT Fake Share Notification

---

##  Overview
This report analyzes a suspicious email claiming to be from an internal IT service. The message attempts to tick the recipient into clicking a malicious link disguised as a legitimate document-sharing notification.

---

## Email Details

- **From:** tbfc-it@tbƒc.com  
- **To:** savoys@tbfc.com  
- **Subject:** TBFC-IT shared "Christmas Laptop Upgrade agreement"
- **Date:** Fri, 12 Dec 2025  

---

##  Phishing Signals Identified

- **Impersonation:** The sender pretends to be "TBFC-IT", an internal IT department  
- **Typosquatting:** Domain `tbƒc.com` uses a deceptive Unicode character instead of `tbfc.com`  
- **Social Engineering:** Message creates trust by implying restricted access ("This link only works for the direct recipients")  
- **Suspicious Link:** Redirects to a non-legitimate domain (`microsoftooline.co`)

---

##  Analysis

### Impersonation
The email mimics an internal IT notification service to gain the recipient’s trust and increase the likelihood of interaction.

---
### Typosquatting
The sender domain `tbƒc.com` contains a Unicode character (“ƒ”) designed to visually resemble a legitimate domain (`tbfc.com`), indicating a domain spoofing attempt.

---
### Social Engineering
The message uses trust-based manipulation by suggesting that the shared document is exclusive to the recipient, encouraging interaction.

---
### Malicious Link
The embedded link (`microsoftooline.co`) is not associated with legitimate Microsoft services and is likely intended to redirect the user to a phishing page for credential harvesting.

---

##  Indicators of Compromise (IOCs)

- **Sender Email:** tbfc-it@tbƒc.com  
- **Typosquatted Domain:** tbƒc.com  
- **Suspicious URL:** https://microsoftooline.co  
- **Return-Path:** tbfc-it@xn--tbc-n5a.com  
- SPF: PASS (authorized sending server)
- DKIM: PASS (signed by different domain – misaligned)
- DMARC: NONE (no policy enforced)

---

## MITRE ATT&CK Mapping

- **T1566.002 – Spearphishing Link**  
- **T1036 – Masquerading**

---
## Conclusion

This email is classified as a phishing attack leveraging impersonation, typosquatting, and social engineering techniques to trick the recipie
nt into clicking a malicious link. Interaction with the link could lead to credential theft or further compromise.
---
## Recommendations / Mitigation

- Do not click on suspicious or unknown links 
- Verify the sender's domain for typosquatting or unusual characters  
- Avoid interacting with emails claiming urgency or exclusivity without verification  
- Report the email to the security team or SOC for further investigation  
- Implement email filtering solutions to detect phishing attempts  
- Ensure DMARC, SPF,DKIM policies are properly configured and enforced


