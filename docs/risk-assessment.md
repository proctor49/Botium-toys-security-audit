# Risk Assessment — Botium Toys

**Document Type:** Risk Assessment Report  
**Analyst:** Junior Security Analyst  
**Date:** June 2026  
**Risk Scoring Method:** Qualitative (Likelihood × Impact)

---

## 1. Risk Assessment Overview

This document provides a structured risk assessment for Botium Toys based on findings from the internal security audit. Risks are evaluated using a qualitative scoring model that considers both the **likelihood** of a threat occurring and the **impact** it would have on the organization.

### Risk Scoring Matrix

| | **Low Impact** | **Medium Impact** | **High Impact** |
|---|---|---|---|
| **High Likelihood** | 🟠 Medium | 🔴 High | 🔴 Critical |
| **Medium Likelihood** | 🟢 Low | 🟠 Medium | 🔴 High |
| **Low Likelihood** | 🟢 Low | 🟢 Low | 🟠 Medium |

---

## 2. Overall Risk Profile

| Metric | Rating | Rationale |
|--------|--------|-----------|
| **Overall Risk Score** | **8 / 10** | Missing critical controls across multiple domains |
| **Asset Impact Rating** | **Medium** | Impact uncertain — assets not yet classified |
| **Regulatory Risk** | **High** | Non-compliance with PCI DSS; partial GDPR compliance |
| **Operational Risk** | **High** | No backups or disaster recovery plan |
| **Insider Threat Risk** | **High** | Unrestricted data access for all employees |

---

## 3. Identified Risks

### RISK-001 | Customer Data Breach via Unencrypted Storage or Transmission

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | External attacker, malicious insider |
| **Threat Event** | Unauthorized access to or interception of credit card data and PII |
| **Vulnerability** | No encryption for data at rest or in transit |
| **Likelihood** | High — unencrypted data is a direct and easily exploited target |
| **Impact** | High — financial loss, regulatory fines (PCI DSS, GDPR), reputational damage |
| **Inherent Risk** | 🔴 **Critical** |
| **Affected Controls** | Encryption (Missing), Access Controls (Missing) |
| **Compliance Risk** | PCI DSS Requirements 3 & 4; GDPR Article 32 |

**Risk Narrative:** Botium Toys stores and processes customer credit card data and PII without encryption. An attacker who gains network access — through phishing, an unpatched vulnerability, or a compromised credential — can directly read and exfiltrate sensitive customer data. The absence of encryption means there is no last-resort protection if perimeter defenses are breached.

---

### RISK-002 | Insider Threat / Privilege Abuse

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | Malicious or negligent insider (employee or vendor) |
| **Threat Event** | Unauthorized access, modification, or exfiltration of sensitive data |
| **Vulnerability** | All employees have unrestricted access to all data; no least privilege |
| **Likelihood** | Medium — insider threats are common; opportunity is currently unlimited |
| **Impact** | High — full access to PII, SPII, and financial data |
| **Inherent Risk** | 🔴 **High** |
| **Affected Controls** | Least Privilege (Missing), Separation of Duties (Missing), Access Control Policy (Missing) |
| **Compliance Risk** | PCI DSS Requirement 7; SOC 2 Confidentiality |

**Risk Narrative:** With no least privilege controls, a disgruntled employee, compromised account, or even a well-meaning but careless employee can access any data in the system. The risk extends to third-party vendors who interact with internal systems.

---

### RISK-003 | Ransomware Attack or Data Loss Event

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | Ransomware operators, hardware failure, natural disaster |
| **Threat Event** | Encryption or destruction of business-critical data and systems |
| **Vulnerability** | No backups of critical data; no disaster recovery plan |
| **Likelihood** | Medium — ransomware is the #1 threat for small-to-medium businesses |
| **Impact** | High — permanent data loss; complete business disruption |
| **Inherent Risk** | 🔴 **High** |
| **Affected Controls** | Backups (Missing), Disaster Recovery Plan (Missing) |
| **Compliance Risk** | SOC 2 Availability; GDPR data availability obligations |

**Risk Narrative:** Without data backups or a disaster recovery plan, a successful ransomware attack — or even a hardware failure — could result in the permanent loss of all customer records, transaction history, and operational data. Botium Toys would have no recovery path and would face both regulatory penalties and potential lawsuits.

---

### RISK-004 | Undetected Network Intrusion

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | External attacker, advanced persistent threat (APT) |
| **Threat Event** | Attacker establishes persistent access; moves laterally through the network |
| **Vulnerability** | No IDS/IPS deployed |
| **Likelihood** | Medium — targeted attacks on e-commerce companies are common |
| **Impact** | High — long dwell time allows maximum data harvesting |
| **Inherent Risk** | 🔴 **High** |
| **Affected Controls** | IDS/IPS (Missing) |
| **Compliance Risk** | PCI DSS Requirement 10 (monitoring) |

**Risk Narrative:** The firewall provides perimeter protection, but once an attacker bypasses it (via phishing, a vulnerable web application, etc.), there is no detection capability inside the network. Attackers could maintain persistent access for months without triggering any alerts.

---

### RISK-005 | Account Compromise via Weak Credentials

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | External attacker using brute force or credential stuffing |
| **Threat Event** | Unauthorized access to employee accounts and business systems |
| **Vulnerability** | Weak password policy; no centralized enforcement; no MFA |
| **Likelihood** | High — credential attacks are extremely common and largely automated |
| **Impact** | Medium — depends on compromised account's access level |
| **Inherent Risk** | 🟠 **Medium–High** |
| **Affected Controls** | Password Policy (Inadequate), Password Management (Missing) |
| **Compliance Risk** | PCI DSS Requirement 8 |

**Risk Narrative:** Weak passwords with no MFA create easy entry points. Given that all employees have unrestricted data access (RISK-002), even a low-level account compromise becomes a critical incident.

---

### RISK-006 | Exploitation of Unpatched Legacy Systems

| Attribute | Detail |
|-----------|--------|
| **Threat Source** | Automated vulnerability scanners, opportunistic attackers |
| **Threat Event** | Exploitation of known CVEs in unpatched, end-of-life systems |
| **Vulnerability** | No formal maintenance schedule; intervention methods undefined |
| **Likelihood** | Medium — legacy systems are commonly targeted |
| **Impact** | Medium — depends on system function and network access |
| **Inherent Risk** | 🟠 **Medium** |
| **Affected Controls** | Legacy System Maintenance (Inadequate) |
| **Compliance Risk** | PCI DSS Requirement 6 (vulnerability management) |

**Risk Narrative:** End-of-life systems no longer receive vendor security patches. Without a defined maintenance schedule, vulnerabilities may persist indefinitely. If legacy systems are connected to the same network segment as sensitive data, exploitation could lead to data exfiltration.

---

## 4. Risk Register Summary

| Risk ID | Description | Likelihood | Impact | Risk Level | Priority |
|---------|-------------|------------|--------|------------|----------|
| RISK-001 | Unencrypted data breach | High | High | 🔴 Critical | 1 |
| RISK-002 | Insider threat / privilege abuse | Medium | High | 🔴 High | 2 |
| RISK-003 | Ransomware / data loss | Medium | High | 🔴 High | 3 |
| RISK-004 | Undetected network intrusion | Medium | High | 🔴 High | 4 |
| RISK-005 | Account compromise | High | Medium | 🟠 Medium-High | 5 |
| RISK-006 | Legacy system exploitation | Medium | Medium | 🟠 Medium | 6 |

---

## 5. Risk Acceptance Statement

The following risks are currently **accepted** due to adequate existing controls:

| Risk | Basis for Acceptance |
|------|----------------------|
| Physical theft / unauthorized access | Physical controls (locks, CCTV, fire systems) are adequate |
| Malware infection | Antivirus is installed and actively monitored |
| Perimeter-level network attack | Firewall with appropriate rule set is in place |

These risks should be **monitored** and controls reviewed annually or following any significant change to the environment.

---

## 6. Residual Risk After Recommended Controls

If all recommended controls from the [Audit Report](audit-report.md) are implemented, estimated residual risk levels are:

| Risk ID | Current Risk | Residual Risk (Post-Remediation) |
|---------|-------------|----------------------------------|
| RISK-001 | 🔴 Critical | 🟢 Low (encryption + access controls) |
| RISK-002 | 🔴 High | 🟢 Low (RBAC + separation of duties) |
| RISK-003 | 🔴 High | 🟢 Low (backups + DRP) |
| RISK-004 | 🔴 High | 🟠 Medium (IDS + SIEM) |
| RISK-005 | 🟠 Medium-High | 🟢 Low (MFA + password manager) |
| RISK-006 | 🟠 Medium | 🟢 Low (maintenance schedule + patching) |

---

*Risk Assessment prepared as part of the Google Cybersecurity Certificate portfolio.*  
*Botium Toys is a fictional company used for educational purposes.*
