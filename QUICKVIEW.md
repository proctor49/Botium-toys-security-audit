#  Botium Toys Security Audit — Internal Controls & Compliance Assessment
Internal security audit and compliance assessment - NIST CSF framework, PCI DSS & amp; GDPR gap analysis.


> **Portfolio Project** | Google Cybersecurity Certificate | Junior Security Analyst

[![Security Audit](https://img.shields.io/badge/Type-Security%20Audit-blue)](https://github.com)
[![Framework](https://img.shields.io/badge/Framework-NIST%20CSF-green)](https://www.nist.gov/cyberframework)
[![Risk Score](https://img.shields.io/badge/Risk%20Score-8%2F10%20(High)-red)](https://github.com)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen)](https://github.com)

---
## 📋 Project Overview

This repository documents a comprehensive internal security audit conducted for **Botium Toys**, a fictional small U.S. toy company with a growing online presence. The audit was performed as part of the **Google Cybersecurity Certificate** program and simulates a real-world security assessment scenario.

The audit evaluates Botium Toys' security posture across administrative, technical, and physical control domains, assesses compliance with industry standards (PCI DSS, GDPR, SOC), and produces prioritized remediation recommendations.

---

### 📁 Repository Structure

```
botium-toys-security-audit/
│
├── README.md                          ← Detailed and structure project with all the steps to the report
|
├── QUICKVIEW.md                       ← You are here
|
├── docs/
|   ├── QUICKVIEW.md                   ← Quick review of the whole project in one page without traveling for quick glance
│   ├── executive-summary.md           ← High-level findings for leadership
│   ├── audit-report.md                ← Full internal audit report
│   └── risk-assessment.md             ← Detailed risk assessment findings
│
├── checklists/
│   ├── controls-assessment.md         ← Security controls checklist
│   └── compliance-checklist.md        ← PCI DSS, GDPR, SOC compliance
│
└── assets/
    └── asset-inventory.md             ← Full IT asset inventory
```

---

####  Table of Contents

- [Executive Summary](#executive-summary)
- [Scope & Goals](#scope--goals)
- [Asset Inventory](#asset-inventory)
- [Risk Assessment Findings](#risk-assessment-findings)
- [Security Controls Assessment](#security-controls-assessment)
- [Compliance Considerations](#compliance-considerations)
- [Identified Vulnerabilities & Risk Ratings](#identified-vulnerabilities--risk-ratings)
- [Recommended Remediation Actions](#recommended-remediation-actions)
- [Conclusion](#conclusion)
- [Skills Demonstrated](#skills-demonstrated)
- [References](#references)

---

##### Executive Summary

| Field | Details |
|---|---|
| **Organization** | Botium Toys |
| **Audit Type** | Internal Security Controls & Compliance Assessment |
| **Analyst** | Junior Cybersecurity Analyst (Portfolio Project) |
| **Framework** | NIST Cybersecurity Framework (CSF) |
| **Overall Risk Score** | **8 / 10 — High** |
| **Audit Date** | JUNE 2026 |

Botium Toys is a small U.S.-based toy retailer with a growing online presence serving customers both domestically and in the European Union. As digital operations expand, the organization's IT infrastructure faces increasing exposure to cybersecurity threats. This internal audit was commissioned to evaluate the current state of Botium Toys' security program across people, processes, and technology.

**Key Findings at a Glance:**

- ❌ No least-privilege or separation-of-duties controls in place
- ❌ Customer credit card data (PCI DSS in scope) stored without encryption
- ❌ No Intrusion Detection System (IDS) deployed
- ❌ No disaster recovery plan or critical data backups
- ❌ Weak password policy with no centralized enforcement
- ✅ Firewall in place with defined security rules
- ✅ Antivirus software installed and monitored
- ✅ Physical security controls (CCTV, locks, fire systems) are adequate
- ✅ GDPR breach notification plan in place for EU customers

The organization must prioritize implementation of access controls, encryption, backup/recovery capabilities, and network monitoring to reduce its overall risk exposure and achieve compliance with PCI DSS and GDPR.

---

## Scope & Goals

### Scope

The audit covers the **entire security program** at Botium Toys, including:

- All employee end-user devices (desktops, laptops, smartphones, workstations)
- Internal network infrastructure
- Retail storefront and adjoining warehouse systems
- Managed systems: accounting, telecommunications, database, e-commerce, and inventory management
- Internet connectivity and data retention/storage
- Legacy systems requiring manual monitoring

### Goals

1. Assess and document all current assets managed by the IT Department
2. Complete a controls and compliance checklist against industry standards
3. Identify gaps between current security posture and best practices
4. Provide actionable, risk-prioritized remediation recommendations to improve security stance 

---

## Asset Inventory

The IT Department manages the following asset categories:

| # | Asset Category | Examples | Sensitivity |
|---|---|---|---|
| 1 | **On-Premises Equipment** | Office hardware, servers | Medium |
| 2 | **Employee End-User Devices** | Desktops, laptops, smartphones, docking stations, headsets | Medium–High |
| 3 | **Remote Workstations** | Remote employee systems | High |
| 4 | **Retail & Warehouse Products** | Physical inventory (on-site and online storefront) | Low–Medium |
| 5 | **Business Systems** | Accounting, telecom, database, e-commerce, inventory mgmt | High |
| 6 | **Network Infrastructure** | Internal network, internet access | High |
| 7 | **Data Storage** | Customer data, cardholder data, PII/SPII | Critical |
| 8 | **Legacy Systems** | End-of-life systems requiring human monitoring | High |
| 9 | **Surveillance Equipment** | CCTV cameras, badge systems | Medium |

> **Gap Identified:** The IT Department currently lacks a formal, classified asset inventory. Without proper asset classification, it is impossible to determine the full impact of potential asset loss on business continuity a core requirement of the NIST CSF *Identify* function.

---

## Risk Assessment Findings

### Risk Score: 8 / 10 (High)

The elevated risk score reflects a combination of missing technical controls, inadequate access governance, and partial compliance adherence. Below is a breakdown of contributing factors:

| Risk Area | Current State | Impact |
|---|---|---|
| Asset Management | No formal classification | Cannot prioritize protection |
| Access Control | All employees can access all data | High likelihood of insider threat or lateral movement |
| Data Encryption | Credit card data stored in plaintext | Regulatory violation (PCI DSS) + data breach exposure |
| Intrusion Detection | No IDS deployed | Threats may go undetected |
| Business Continuity | No DR plan, no backups | Full data loss possible in an incident |
| Password Security | Weak policy, no centralized management | Susceptible to brute-force attacks |
| Legacy Systems | No maintenance schedule | Unpatched vulnerabilities persist |
| Compliance | Partial PCI DSS, partial GDPR | Risk of regulatory fines |

### Risk Likelihood vs. Impact Matrix

```
Impact
  ^
  |  [Encryption Gap]   [No IDS]
H |  [No Backups/DR]    [Access Control Gap]
  |
M |  [Password Policy]  [Legacy Systems]
  |
L |  [Asset Inventory]  [Physical Controls] ✅
  +-------------------------------------> Likelihood
       Low               High
```

---

## Security Controls Assessment

Assessment of controls across all three categories, mapped against current implementation status:

### Administrative / Managerial Controls

| Control | Type | Status | Priority |
|---|---|---|---|
| Least Privilege | Preventative | ❌ Not Implemented | 🔴 High |
| Separation of Duties | Preventative | ❌ Not Implemented | 🔴 High |
| Disaster Recovery Plans | Corrective | ❌ Not Implemented | 🔴 High |
| Password Policies | Preventative | ⚠️ Partial (weak requirements) | 🟡 Medium |
| Access Control Policies | Preventative | ❌ Not Implemented | 🔴 High |
| Account Management Policies | Preventative | ❌ Not Implemented | 🔴 High |

### Technical Controls

| Control | Type | Status | Priority |
|---|---|---|---|
| Firewall | Preventative | ✅ Implemented | — |
| IDS/IPS | Detective | ❌ Not Implemented | 🔴 High |
| Encryption | Deterrent | ❌ Not Implemented | 🔴 High |
| Backups | Corrective | ❌ Not Implemented | 🔴 High |
| Password Management System | Preventative | ❌ Not Implemented | 🟡 Medium |
| Antivirus (AV) Software | Corrective | ✅ Implemented & Monitored | — |
| Legacy System Monitoring | Preventative | ⚠️ Partial (no schedule) | 🟡 Medium |

### Physical Controls

| Control | Type | Status | Priority |
|---|---|---|---|
| Adequate Locks | Deterrent/Preventative | ✅ Implemented | — |
| CCTV Surveillance | Preventative/Detective | ✅ Implemented (up-to-date) | — |
| Fire Detection & Prevention | Detective/Preventative | ✅ Implemented | — |
| Time-Controlled Safe | Deterrent | ⚠️ Not Assessed | 🟢 Low |
| Locking Cabinets (Network Gear) | Preventative | ⚠️ Not Assessed | 🟡 Medium |
| Signage (Alarm Provider) | Deterrent | ⚠️ Not Assessed | 🟢 Low |

**Summary:**

```
Controls Implemented:     4 / 16  (25%)
Partially Implemented:    4 / 16  (25%)
Not Implemented:          8 / 16  (50%)
```

---

## Compliance Considerations

Botium Toys processes online payments and serves EU customers, making it subject to both **PCI DSS** and **GDPR**. The following table maps current gaps to specific regulatory requirements:

### PCI DSS (Payment Card Industry Data Security Standard)

| PCI DSS Requirement | Current Status | Risk |
|---|---|---|
| Protect cardholder data with encryption | ❌ Encryption not in use | 🔴 High — Direct violation |
| Restrict access to cardholder data by business need | ❌ All employees have access | 🔴 High — Direct violation |
| Implement strong access control measures | ❌ No least privilege or separation of duties | 🔴 High |
| Regularly test security systems and processes | ❌ No IDS, no scheduled testing | 🔴 High |
| Maintain a vulnerability management program | ⚠️ AV in place; no IDS or formal program | 🟡 Medium |
| Maintain an information security policy | ⚠️ Partial policies exist | 🟡 Medium |

> **Risk:** Failure to comply with PCI DSS may result in **significant fines, loss of payment processing privileges, and reputational damage**.

### GDPR (General Data Protection Regulation)

| GDPR Requirement | Current Status | Risk |
|---|---|---|
| Protect EU customer personal data (PII/SPII) | ❌ Encryption not in use; broad access | 🔴 High |
| Notify supervisory authority within 72 hours of breach | ✅ Plan established | — |
| Data minimization and purpose limitation | ❌ All employees can access all data | 🔴 High |
| Maintain documented data handling procedures | ✅ Privacy policies enforced | — |
| Data integrity controls | ✅ IT has implemented integrity controls | — |

> **Risk:** Non-compliance with GDPR exposes Botium Toys to fines of up to **€20 million or 4% of global annual turnover**, whichever is higher.

---

## Identified Vulnerabilities & Risk Ratings

| # | Vulnerability | Category | Risk Rating | Regulatory Impact |
|---|---|---|---|---|
| V-01 | All employees can access all internal data including PII/SPII | Access Control | 🔴 **High** | PCI DSS, GDPR |
| V-02 | Customer credit card data stored without encryption | Data Protection | 🔴 **High** | PCI DSS, GDPR |
| V-03 | No least-privilege or separation-of-duties controls | Access Control | 🔴 **High** | PCI DSS |
| V-04 | No Intrusion Detection System (IDS) deployed | Network Security | 🔴 **High** | PCI DSS |
| V-05 | No disaster recovery plan in place | Business Continuity | 🔴 **High** | General |
| V-06 | No backups of critical data | Business Continuity | 🔴 **High** | General |
| V-07 | Password policy is weak and not enforced centrally | Identity & Access | 🟡 **Medium** | PCI DSS |
| V-08 | No centralized password management system | Identity & Access | 🟡 **Medium** | PCI DSS |
| V-09 | Legacy systems monitored without a defined schedule | Asset Management | 🟡 **Medium** | General |
| V-10 | No formal asset classification or inventory | Asset Management | 🟡 **Medium** | General |
| V-11 | Locking cabinets for network gear not confirmed | Physical Security | 🟢 **Low** | General |
| V-12 | Time-controlled safe status not assessed | Physical Security | 🟢 **Low** | General |

### Risk Rating Definitions

| Rating | Score | Description |
|---|---|---|
| 🔴 **High** | 7–10 | Immediate action required; significant business or regulatory impact |
| 🟡 **Medium** | 4–6 | Action required within near-term planning cycle |
| 🟢 **Low** | 1–3 | Monitor and address as resources permit |

---

## Recommended Remediation Actions

Recommendations are prioritized by risk rating. Each recommendation includes the security rationale.

### 🔴 Priority 1 — High Risk (Immediate Action Required)

---

#### REC-01: Implement Least Privilege & Separation of Duties
**Addresses:** V-01, V-03 | **Frameworks:** PCI DSS Req. 7, GDPR Art. 5

**Action Steps:**
- Conduct a role-based access control (RBAC) review for all staff roles
- Assign data access permissions based on job function only
- Implement separation of duties for critical financial and administrative functions
- Revoke broad access to cardholder data and PII/SPII for non-essential personnel

**Why this improves security:** Limiting access to only what each employee needs to perform their job (least privilege) dramatically reduces the attack surface. If a user account is compromised, the attacker's lateral movement is constrained. Separation of duties prevents any single person from having unchecked control over critical processes, reducing fraud and insider threat risk.

---

#### REC-02: Encrypt Cardholder and Customer PII/SPII Data
**Addresses:** V-02 | **Frameworks:** PCI DSS Req. 3 & 4, GDPR Art. 32

**Action Steps:**
- Implement AES-256 encryption for all stored cardholder data
- Enforce TLS 1.2/1.3 for all data in transit (payment flows, APIs, internal comms)
- Conduct a data flow audit to identify all locations where sensitive data is stored or transmitted
- Implement tokenization for payment data where possible

**Why this improves security:** Encryption ensures that even if sensitive data is accessed by an unauthorized party, it is rendered unreadable without the decryption key. This is the primary technical safeguard for confidentiality and a hard requirement under both PCI DSS and GDPR.

---

#### REC-03: Deploy an Intrusion Detection System (IDS)
**Addresses:** V-04 | **Frameworks:** PCI DSS Req. 10 & 11

**Action Steps:**
- Deploy a network-based IDS (NIDS) to monitor traffic on internal segments
- Configure alert rules based on known threat signatures and anomalous behavior baselines
- Integrate IDS alerts with a Security Information and Event Management (SIEM) system or centralized log management
- Assign responsibility for monitoring and triaging IDS alerts to IT staff

**Why this improves security:** An IDS provides detective capability — without it, malicious activity such as network scanning, lateral movement, or data exfiltration may go completely undetected. Early detection shortens dwell time and limits breach impact.

---

#### REC-04: Develop and Test a Disaster Recovery Plan (DRP)
**Addresses:** V-05, V-06 | **Frameworks:** NIST CSF — Recover, ISO 22301

**Action Steps:**
- Define Recovery Time Objectives (RTO) and Recovery Point Objectives (RPO) for all critical systems
- Implement automated, encrypted backups of all critical data (following the 3-2-1 rule: 3 copies, 2 media types, 1 offsite)
- Document system recovery procedures for all key platforms (e-commerce, database, accounting)
- Conduct a tabletop exercise to validate the DRP at least annually

**Why this improves security:** Without backups and a recovery plan, a ransomware attack, hardware failure, or natural disaster could permanently destroy business-critical data and halt operations. A tested DRP ensures the organization can recover quickly and predictably from any incident, preserving business continuity.

---

### 🟡 Priority 2 — Medium Risk (Address Within Planning Cycle)

---

#### REC-05: Strengthen and Enforce the Password Policy
**Addresses:** V-07, V-08 | **Frameworks:** PCI DSS Req. 8, NIST SP 800-63B

**Action Steps:**
- Update the password policy to require a minimum of 12 characters, including uppercase, lowercase, numbers, and special characters
- Enforce password history (no reuse of last 10 passwords) and maximum age (90 days or less)
- Deploy a centralized password management solution (e.g., enterprise password vault) with policy enforcement
- Enable Multi-Factor Authentication (MFA) for all privileged accounts and remote access

**Why this improves security:** Weak passwords are one of the most common attack vectors. A strong, enforced password policy raises the cost of brute-force and credential-stuffing attacks. Centralized management removes human inconsistency and eliminates the productivity drain of ad-hoc IT password resets. MFA provides a critical second layer of authentication, even if a password is compromised.

---

#### REC-06: Establish a Legacy System Maintenance Schedule
**Addresses:** V-09 | **Frameworks:** NIST CSF — Protect, PCI DSS Req. 6

**Action Steps:**
- Inventory all legacy/end-of-life systems and document their function and data access
- Define a recurring maintenance and monitoring schedule (e.g., monthly reviews)
- Document intervention procedures and escalation paths for anomalies detected on legacy systems
- Develop a migration/decommission roadmap for systems that cannot be patched

**Why this improves security:** Legacy systems often contain unpatched vulnerabilities that cannot be remediated through standard vendor updates. Without a schedule, monitoring is ad-hoc and inconsistent, creating unpredictable security gaps. Clear procedures ensure timely detection and response to issues on these high-risk systems.

---

#### REC-07: Conduct a Formal Asset Classification Exercise
**Addresses:** V-10 | **Frameworks:** NIST CSF — Identify (ID.AM)

**Action Steps:**
- Enumerate all assets using automated discovery tools
- Classify assets by data sensitivity (Public, Internal, Confidential, Restricted)
- Assign asset owners from relevant business units
- Maintain a living asset register updated at least quarterly

**Why this improves security:** You cannot protect what you cannot see. A complete, classified asset inventory is foundational to every other security control. It enables accurate risk assessment, appropriate security investment, and informed incident response. This directly addresses the NIST CSF Identify function gap noted in the audit.

---

### 🟢 Priority 3 — Low Risk (Monitor & Address As Resources Permit)

---

#### REC-08: Verify Physical Security of Network Infrastructure
**Addresses:** V-11, V-12

**Action Steps:**
- Conduct a physical walkthrough to confirm locking cabinets are in use for all network gear (switches, routers, patch panels)
- Verify a time-controlled safe is present and in use for sensitive physical assets
- Ensure alarm system provider signage is visible at entry points as a deterrent

**Why this improves security:** Physical access to network infrastructure can allow an attacker to bypass all logical controls — plugging in a rogue device, intercepting traffic, or causing hardware damage. Locking cabinets and controlled safes are low-cost, high-impact deterrents.

---

## Conclusion

Botium Toys' current security posture presents a **high level of risk** with a score of **8/10** — driven primarily by the absence of fundamental access controls, encryption of sensitive data, network intrusion detection, and business continuity planning. While the organization has some foundational controls in place (firewall, antivirus, physical security, and a GDPR breach notification procedure), the gaps in technical and administrative controls leave both customer data and business operations significantly exposed.

### Remediation Priority Summary

| Priority | Controls to Implement | Risk Reduced |
|---|---|---|
| 🔴 Immediate | Least privilege, encryption, IDS, DR/backups | V-01 through V-06 |
| 🟡 Short-Term | Password policy, legacy scheduling, asset inventory | V-07 through V-10 |
| 🟢 Ongoing | Physical control verification, policy reviews | V-11, V-12 |

If the Priority 1 recommendations are implemented, the estimated risk score would decrease from **8/10 to approximately 4/10**, moving the organization from a high-risk to a moderate-risk posture. Full implementation of all recommendations would further reduce risk to an acceptable level and bring the organization into compliance with PCI DSS and GDPR.

> **Next Steps:** Botium Toys' IT leadership should present these findings to executive stakeholders, allocate budget for Priority 1 controls, and schedule a follow-up audit within 90 days of implementing major changes to verify effectiveness.

---

## Skills Demonstrated

This project showcases the following cybersecurity concepts and competencies:

| Skill Area | Concepts Applied |
|---|---|
| **Security Frameworks** | NIST Cybersecurity Framework (CSF) — Identify, Protect, Detect, Respond, Recover functions |
| **Risk Assessment** | Qualitative risk scoring, likelihood vs. impact analysis, risk rating classification |
| **Security Controls Analysis** | Administrative, technical, and physical control evaluation; control type classification (preventative, corrective, detective, deterrent) |
| **Compliance & Regulatory Knowledge** | PCI DSS requirements mapping, GDPR Article analysis, compliance gap identification |
| **Vulnerability Identification** | Systematic vulnerability enumeration, categorization, and prioritization |
| **Access Control Principles** | Least privilege, separation of duties, role-based access control (RBAC) |
| **Data Protection** | Encryption standards (AES-256, TLS), tokenization, data classification |
| **Network Security** | Firewall evaluation, IDS/IPS concepts, network monitoring |
| **Business Continuity Planning** | DR plan development, RTO/RPO concepts, backup strategy (3-2-1 rule) |
| **Identity & Access Management** | Password policy design, MFA, centralized password management |
| **Asset Management** | Asset inventory, classification, and lifecycle management |
| **Security Communication** | Executive-level risk reporting, technical documentation, remediation roadmaps |
| **Physical Security** | CCTV, access controls, environmental controls assessment |
| **Audit Methodology** | Structured audit scoping, evidence-based findings, control checklists |

---

## References

- [NIST Cybersecurity Framework (CSF) v1.1](https://www.nist.gov/cyberframework)
- [PCI DSS v3.2.1 — PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [GDPR — Official EU Regulation Text](https://gdpr-info.eu/)
- [NIST SP 800-63B — Digital Identity Guidelines](https://pages.nist.gov/800-63-3/sp800-63b.html)
- [ISO/IEC 27001 — Information Security Management](https://www.iso.org/isoiec-27001-information-security.html)
- [Google Cybersecurity Certificate](https://grow.google/certificates/cybersecurity/)

---

*This project was completed as part of the Google Cybersecurity Certificate program. It is intended as a portfolio artifact demonstrating security audit and risk assessment skills. All company and scenario details are fictional and for educational purposes only.*

<div align="center">

**Connect with me:**
[LinkedIn] www.linkedin.com/in/jillzprocta49sec | [GitHub]https://github.com/proctor49

*Junior Cybersecurity Analyst | Google Cybersecurity Certificate Candidate*

</div>

---

