# MediSure Healthcare Phishing Investigation & Incident Response

## Project Overview

This project simulates a Security Operations Center (SOC) investigation into a phishing campaign targeting employees of MediSure Health Network, a healthcare organization responsible for protecting sensitive patient information and financial data.

The investigation focused on a suspicious email impersonating Microsoft and warning recipients about unusual sign-in activity. Through email analysis, authentication validation, threat intelligence enrichment, and SIEM correlation, the email was confirmed to be a phishing attempt.

---

## Objectives

* Analyze suspicious email headers
* Validate SPF, DKIM, and DMARC authentication records
* Assess domain and IP reputation
* Identify indicators of compromise (IOCs)
* Correlate user activity using Splunk
* Determine affected users and systems
* Develop containment and remediation actions
* Produce an Incident Response Plan

---

## Tools Used

* Splunk Enterprise
* PhishTool
* MXToolbox
* VirusTotal
* SpamAssassin

---

## Investigation Workflow

### 1. Email Analysis

The suspicious email was analyzed using PhishTool and email header inspection.

Findings included:

* Suspicious Reply-To address
* Microsoft impersonation
* External sender infrastructure
* Social engineering techniques

---

### 2. Authentication Validation

Authentication controls were reviewed using MXToolbox and SpamAssassin.

Findings:

* SPF Failure
* Missing DKIM Signature
* Missing DMARC Record

---

### 3. Threat Intelligence Enrichment

VirusTotal was used to investigate domains and IP addresses associated with the phishing campaign.

Investigated IOCs:

* access-accsecurity.com
* sign.in
* 89.144.44.41
* 103.225.77.255

---

### 4. Splunk Threat Hunting

Splunk searches identified:

* Russian authentication activity
* Users accessing phishing infrastructure
* Internal hosts communicating with attacker IPs
* Affected user accounts

---

## Key Findings

### Affected Users

* [alice@medisurehealthnetwork.com](mailto:alice@medisurehealthnetwork.com)
* [bob@medisurehealthnetwork.com](mailto:bob@medisurehealthnetwork.com)

### Malicious Infrastructure

Domains:

* access-accsecurity.com
* sign.in

IPs:

* 89.144.44.41
* 103.225.77.255

### Authentication Issues

* SPF Failed
* DKIM Missing
* DMARC Missing

### SpamAssassin Detection

* Score: 6.6
* Threshold: 5.0
* Classified as Suspicious

---

## Incident Response Actions

* Blocked malicious domains
* Blocked attacker IP addresses
* Isolated affected accounts
* Forced password resets
* Updated email filtering rules
* Enhanced phishing detection controls

---

## MITRE ATT&CK Mapping

| Technique             | ATT&CK ID |
| --------------------- | --------- |
| Phishing              | T1566     |
| Spearphishing Link    | T1566.002 |
| Credential Harvesting | T1056     |
| User Execution        | T1204     |
| Valid Accounts        | T1078     |
| Masquerading          | T1036     |

---

## Project Outcome

The phishing campaign was successfully identified, investigated, and contained. The investigation demonstrated practical SOC analyst skills including email analysis, threat hunting, IOC enrichment, log correlation, incident response, and security reporting.

## Author

Daniel Nwachukwu

SOC Analyst | Threat Detection & Incident Response | SIEM Engineering (Wazuh, Splunk, ELK)
