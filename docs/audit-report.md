# Internal Security Audit Report — Botium Toys

**Report Type:** Internal Security Audit  
**Analyst:** Junior Security Analyst  
**Audit Period:** June 2026  
**Methodology:** NIST Cybersecurity Framework (CSF)  
**Classification:** Internal Use Only

---

## 1. Introduction

### 1.1 Background

Botium Toys is a small U.S.-based toy retailer with a physical storefront and a growing e-commerce presence. The company processes customer credit card transactions online and in-store, and stores customer personally identifiable information (PII) and sensitive PII (SPII). As the business has expanded its digital footprint, its security controls and compliance posture have not kept pace with the associated risks.

This audit was initiated to evaluate the current state of Botium Toys' information security program and identify gaps that could expose the company to data breaches, regulatory penalties, or business disruption.

### 1.2 Audit Objectives

- Identify and classify all IT-managed assets
- Evaluate existing security controls across administrative, technical, and physical domains
- Assess compliance with applicable regulatory frameworks (PCI DSS, GDPR, SOC)
- Determine the risk rating for identified vulnerabilities
- Provide actionable, prioritized remediation recommendations

### 1.3 Methodology

This audit was conducted using the **NIST Cybersecurity Framework (CSF)**, which organizes security activities into five core functions:

| Function | Description |
|----------|-------------|
| **Identify** | Understand the organization's assets, risks, and environment |
| **Protect** | Implement safeguards to ensure delivery of critical services |
| **Detect** | Develop capabilities to identify cybersecurity events |
| **Respond** | Take action regarding detected cybersecurity incidents |
| **Recover** | Maintain resilience and restore capabilities after an incident |

---

## 2. Scope

The scope of this audit encompasses the **entire security program** at Botium Toys, including:

- All IT-managed assets (hardware, software, data, services)
- Internal network infrastructure
- Physical security of the store, offices, and warehouse
- Data handling practices for customer PII, SPII, and cardholder data
- Compliance with PCI DSS, GDPR, and SOC frameworks

---

## 3. Asset Overview

Refer to the [Asset Inventory](../assets/asset-inventory.md) for a complete listing. Key asset categories include:

| Asset Category | Examples |
|----------------|---------|
| End-user Devices | Desktops, laptops, smartphones, remote workstations |
| Peripheral Equipment | Headsets, keyboards, mice, docking stations, cables |
| Surveillance Equipment | Cameras (office, storefront, warehouse) |
| Business Systems | Accounting, telecom, database, ecommerce, inventory mgmt |
| Infrastructure | Internal network, internet access, data storage |
| Legacy Systems | End-of-life systems requiring manual monitoring |
| Physical Inventory | Products in storefront and warehouse |

**Gap Identified:** The IT department lacks a formal, classified asset inventory. The organization cannot fully assess the impact of asset loss on business continuity because assets have not been categorized by criticality or sensitivity.

---

## 4. Risk Assessment Summary

| Metric | Rating |
|--------|--------|
| Overall Risk Score | **8 / 10 (High)** |
| Asset Loss Impact | **Medium** (assets not yet classified) |
| Regulatory/Fine Risk | **High** (compliance gaps identified) |

The high risk score reflects the absence of fundamental security controls (encryption, access controls, IDS, DR planning) and partial non-compliance with PCI DSS and GDPR.

> See the full [Risk Assessment](risk-assessment.md) for detailed threat scenarios and impact analysis.

---

## 5. Security Controls Assessment

### 5.1 Administrative / Managerial Controls

| Control | Status | Risk Level | Finding |
|---------|--------|------------|---------|
| Least Privilege | ❌ Not Implemented | 🔴 High | All employees have unrestricted access to internal data including PII/SPII and cardholder data |
| Separation of Duties | ❌ Not Implemented | 🔴 High | No role-based access separation; any account compromise yields full data access |
| Disaster Recovery Plan | ❌ Not Implemented | 🔴 High | No documented DRP or BCP; no critical data backups exist |
| Access Control Policies | ❌ Not Implemented | 🔴 High | No formal access control policy governing who can access which data or systems |
| Password Policy | ⚠️ Inadequate | 🟠 Medium | Policy exists but is weak; does not meet modern complexity standards |
| Account Management Policy | ❌ Not Implemented | 🟠 Medium | No defined lifecycle for user accounts (onboarding/offboarding procedures unclear) |

**NIST CSF Functions Impacted:** Identify, Protect

---

### 5.2 Technical Controls

| Control | Status | Risk Level | Finding |
|---------|--------|------------|---------|
| Encryption | ❌ Not Implemented | 🔴 High | Customer credit card data stored, processed, and transmitted without encryption — violates PCI DSS |
| Backups | ❌ Not Implemented | 🔴 High | No backups of critical data; full data loss possible from a single incident |
| IDS/IPS | ❌ Not Implemented | 🟠 Medium | No intrusion detection system; active threats may go undetected indefinitely |
| Password Management System | ❌ Not Implemented | 🟠 Medium | No centralized enforcement; employees submit IT tickets for resets, reducing productivity |
| Legacy System Maintenance | ⚠️ Inadequate | 🟠 Medium | Systems monitored but no formal schedule or response procedures defined |
| Firewall | ✅ Implemented | 🟢 Low | Firewall in place with an appropriately defined security rule set |
| Antivirus (AV) Software | ✅ Implemented | 🟢 Low | AV installed and monitored regularly by IT staff |

**NIST CSF Functions Impacted:** Protect, Detect, Recover

---

### 5.3 Physical Controls

| Control | Status | Risk Level | Finding |
|---------|--------|------------|---------|
| CCTV Surveillance | ✅ Implemented | 🟢 Low | Up-to-date CCTV covering storefront, offices, and warehouse |
| Physical Locks | ✅ Implemented | 🟢 Low | Sufficient physical locks on all access points |
| Fire Detection/Prevention | ✅ Implemented | 🟢 Low | Functioning fire alarms and suppression systems in place |
| Locking Cabinets (Network Gear) | ❓ Unverified | 🟠 Medium | Not specifically confirmed; network gear security should be verified |
| Time-Controlled Safe | ❌ Not Implemented | 🟠 Medium | No time-controlled safe for sensitive physical assets identified |
| Adequate Lighting | ❓ Unverified | 🟢 Low | Not confirmed in scope documentation; should be verified |

**NIST CSF Functions Impacted:** Protect, Detect

---

## 6. Compliance Assessment

### 6.1 PCI DSS (Payment Card Industry Data Security Standard)

Applies because Botium Toys accepts, processes, stores, and transmits credit card data.

| Requirement | Status | Detail |
|-------------|--------|--------|
| Restrict access to cardholder data by business need-to-know | ❌ Fail | All employees can access cardholder data |
| Do not store sensitive authentication data after authorization | ❌ Fail | Encryption status unknown; data stored locally without encryption |
| Encrypt transmission of cardholder data across open networks | ❌ Fail | No encryption implemented for cardholder data |
| Implement strong access control measures | ❌ Fail | No least privilege or separation of duties |

**PCI DSS Status: Non-Compliant** — Fines range from $5,000–$100,000/month and can include loss of payment processing privileges.

---

### 6.2 GDPR (General Data Protection Regulation)

Applies because Botium Toys conducts e-commerce and handles data from EU customers.

| Requirement | Status | Detail |
|-------------|--------|--------|
| Notify supervisory authority within 72 hours of a data breach | ✅ Pass | Breach notification plan is in place |
| Maintain documentation of data processing activities | ✅ Pass | Privacy policies and procedures documented and enforced |
| Ensure data is processed lawfully and with appropriate access controls | ❌ Fail | No least privilege; all employees can access EU customer data |
| Implement appropriate technical safeguards | ❌ Fail | No encryption for PII/SPII data |

**GDPR Status: Partial Compliance** — Notification procedures exist, but access and technical controls are insufficient.

---

### 6.3 SOC 1 / SOC 2

Evaluates controls relevant to financial reporting (SOC 1) and security/confidentiality (SOC 2).

| Principle | Status | Detail |
|-----------|--------|--------|
| User Access Controls | ❌ Fail | Least privilege not implemented |
| Data Confidentiality | ❌ Fail | No encryption; all employees have data access |
| Data Integrity | ✅ Pass | IT has ensured availability and data integrity controls |
| Availability | ✅ Pass | Systems available; however, no backup/DR plan creates future risk |

**SOC Status: Non-Compliant** — Confidentiality and access control principles not met.

---

## 7. Identified Vulnerabilities & Recommendations

### 7.1 Critical Vulnerabilities

---

#### V-001 | Absence of Data Encryption
**Risk Level:** 🔴 Critical  
**Affected Assets:** Customer database (credit card data, PII/SPII)  
**Threat:** Data exfiltration, man-in-the-middle attacks, insider data theft  
**Compliance Impact:** PCI DSS, GDPR, SOC 2  

**Current State:** Customer credit card information is accepted, processed, transmitted, and stored in the company's internal database without encryption.

**Recommendation:** Implement AES-256 encryption for data at rest and TLS 1.2/1.3 for data in transit. Ensure encryption keys are managed through a dedicated Key Management System (KMS). Prioritize cardholder data and PII/SPII fields.

**Why This Matters:** Encryption ensures that even if an attacker gains access to the database or intercepts network traffic, the data remains unreadable. This is the single most impactful control for reducing breach severity and achieving PCI DSS compliance.

---

#### V-002 | No Least Privilege or Separation of Duties
**Risk Level:** 🔴 Critical  
**Affected Assets:** All internally stored data, cardholder database, PII/SPII  
**Threat:** Insider threat, privilege escalation, compromised account leading to full data exposure  
**Compliance Impact:** PCI DSS, GDPR, SOC 1/2  

**Current State:** All employees have unrestricted access to all internally stored data, including sensitive customer records.

**Recommendation:** Conduct a role-based access control (RBAC) review. Assign permissions based on job function (need-to-know principle). Implement separation of duties so no single employee can perform high-risk actions alone (e.g., approving and executing financial transactions).

**Why This Matters:** Limiting access reduces the blast radius of any single account compromise. If a phishing attack compromises a warehouse employee's credentials, RBAC ensures they cannot access the financial database.

---

#### V-003 | No Disaster Recovery Plan or Data Backups
**Risk Level:** 🔴 Critical  
**Affected Assets:** All business-critical systems and data  
**Threat:** Ransomware, hardware failure, natural disaster, permanent data loss  
**Compliance Impact:** SOC 2 (Availability), GDPR  

**Current State:** No disaster recovery plan (DRP) or business continuity plan (BCP) exists. No backups of critical data are maintained.

**Recommendation:** Develop a formal DRP/BCP documented to industry standards (ISO 22301). Implement automated daily backups using the 3-2-1 rule: 3 copies of data, on 2 different media types, with 1 copy stored offsite (or in a separate cloud region). Test recovery procedures at least quarterly.

**Why This Matters:** Without backups, a single ransomware infection or hardware failure can result in complete, permanent loss of business and customer data. A tested DRP ensures the business can recover within defined recovery time objectives (RTOs).

---

### 7.2 Significant Vulnerabilities

---

#### V-004 | No Intrusion Detection System (IDS)
**Risk Level:** 🟠 High  
**Affected Assets:** Internal network  
**Threat:** Undetected intrusions, lateral movement, persistent threat actors  

**Current State:** No IDS/IPS is deployed. The firewall blocks known bad traffic, but post-perimeter anomalous activity will go undetected.

**Recommendation:** Deploy a network-based IDS (e.g., Snort, Suricata) and/or a host-based IDS (HIDS) on critical servers. Consider a SIEM solution to aggregate and correlate logs. Configure alerting for suspicious patterns such as port scanning, unusual login times, or large data exfiltration.

**Why This Matters:** A firewall is a preventive control — it blocks known threats at the perimeter. An IDS is a detective control — it identifies threats that have already entered the network. Both layers are necessary for a defense-in-depth strategy.

---

#### V-005 | Weak Password Policy and No Centralized Password Management
**Risk Level:** 🟠 Medium  
**Affected Assets:** All systems with user authentication  
**Threat:** Brute force attacks, credential stuffing, account takeover  

**Current State:** A password policy exists but does not require sufficient complexity. There is no centralized password management system. Password resets are handled manually via IT help desk tickets.

**Recommendation:** Update the password policy to require: minimum 12 characters, upper and lowercase letters, numbers, and at least one special character. Implement a centralized password manager (e.g., LastPass, 1Password Business, or self-hosted Bitwarden). Enable multi-factor authentication (MFA) on all critical systems.

**Why This Matters:** Weak passwords are one of the most common attack vectors. A centralized password manager eliminates password reuse, enforces policy, and reduces IT help desk burden.

---

#### V-006 | No Scheduled Legacy System Maintenance
**Risk Level:** 🟠 Medium  
**Affected Assets:** End-of-life legacy systems  
**Threat:** Unpatched vulnerabilities, system failures, unclear incident response  

**Current State:** Legacy systems are monitored and maintained, but without a defined schedule or documented intervention procedures.

**Recommendation:** Create a formal maintenance schedule for all legacy systems, including patch review frequency, health check procedures, and documented escalation/intervention steps. Evaluate each legacy system for replacement or migration to supported platforms.

**Why This Matters:** End-of-life systems no longer receive vendor security patches, making them permanent targets. A defined maintenance schedule reduces the window of exposure and ensures issues are caught proactively.

---

### 7.3 Low-Risk / Adequate Controls

| Control | Status | Note |
|---------|--------|------|
| Firewall | ✅ Adequate | Maintain and review rules quarterly |
| Antivirus | ✅ Adequate | Continue regular monitoring; ensure definitions updated daily |
| CCTV | ✅ Adequate | Retain footage per data retention policy |
| Physical Locks | ✅ Adequate | Conduct periodic physical access audits |
| Fire Systems | ✅ Adequate | Schedule annual inspections |

---

## 8. Remediation Roadmap

### Immediate (0–30 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Begin encryption implementation for cardholder data and PII | IT / Security | 🔴 Critical |
| Audit all user accounts and begin RBAC design | IT / HR | 🔴 Critical |
| Initiate disaster recovery planning project | IT / Management | 🔴 Critical |

### Short-Term (30–90 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Deploy IDS on internal network | IT / Security | 🟠 High |
| Implement centralized password management with MFA | IT | 🟠 High |
| Update and enforce password policy | IT / HR | 🟠 Medium |
| Create legacy system maintenance schedule | IT | 🟠 Medium |
| Formalize asset inventory with sensitivity classification | IT | 🟠 Medium |

### Long-Term (90–180 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Complete DRP/BCP documentation and first tabletop exercise | IT / Management | 🟠 High |
| Full RBAC implementation and access reviews | IT | 🟠 High |
| Conduct PCI DSS self-assessment or hire QSA | Management | 🔴 Critical |
| GDPR data processing audit with legal counsel | Management / Legal | 🟠 High |

---

## 9. Conclusion

Botium Toys' current security posture presents significant risk to the organization, its customers, and its continued operation. The combination of missing encryption, unrestricted data access, and the absence of disaster recovery planning creates a scenario where a single successful attack could result in regulatory fines, litigation, reputational damage, and potentially irreversible business disruption.

The good news is that Botium Toys has a functional foundation: a properly configured firewall, active antivirus monitoring, and adequate physical security are all in place. By building on these controls and addressing the critical gaps identified in this report — particularly encryption, access controls, and business continuity planning — Botium Toys can achieve a significantly improved security posture within six months.

**A follow-up audit is recommended within 90 days** to assess progress against the remediation roadmap.

---

*Report prepared as part of the Google Cybersecurity Certificate portfolio.*  
*Botium Toys is a fictional company used for educational purposes.*
