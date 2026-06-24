# Compliance Checklist — Botium Toys

**Analyst:** Junior Security Analyst  
**Date:** June 2026  
**Frameworks Assessed:** PCI DSS v4.0 | GDPR | SOC 1 / SOC 2

---

## Why These Frameworks Apply

| Framework | Why It Applies to Botium Toys |
|-----------|-------------------------------|
| **PCI DSS** | Botium Toys accepts, processes, stores, and transmits credit card payment data online and in-store |
| **GDPR** | The company's e-commerce platform serves EU customers, whose data is subject to GDPR protections |
| **SOC 1 / SOC 2** | Applicable as a baseline for internal controls over financial reporting (SOC 1) and security/confidentiality (SOC 2) |

---

## Part 1 — PCI DSS Compliance

**PCI DSS (Payment Card Industry Data Security Standard)** is a mandatory security standard for any organization that handles branded credit cards.

| Req # | Requirement | Status | Findings |
|-------|-------------|--------|----------|
| 1 | Install and maintain network security controls (firewall) | ✅ Pass | Firewall configured with appropriate rule set |
| 2 | Apply secure configurations to all system components | ⚠️ Partial | Legacy systems lack formal configuration management |
| 3 | Protect stored account data | ❌ Fail | Credit card data stored without encryption |
| 4 | Protect cardholder data with strong cryptography during transmission | ❌ Fail | No encryption confirmed for data in transit |
| 5 | Protect all systems against malware | ✅ Pass | Antivirus installed and regularly monitored |
| 6 | Develop and maintain secure systems and software | ⚠️ Partial | No vulnerability management or patching schedule for legacy systems |
| 7 | Restrict access to system components and cardholder data by business need to know | ❌ Fail | All employees have unrestricted access to cardholder data |
| 8 | Identify users and authenticate access to system components | ❌ Fail | Weak password policy; no MFA; no centralized access management |
| 9 | Restrict physical access to cardholder data | ⚠️ Partial | Physical locks and CCTV in place; network gear security unconfirmed |
| 10 | Log and monitor all access to system components and cardholder data | ❌ Fail | No IDS; logging and monitoring capabilities not confirmed |
| 11 | Test security of systems and networks regularly | ❌ Fail | No evidence of regular penetration testing or vulnerability scanning |
| 12 | Support information security with organizational policies and programs | ⚠️ Partial | Some policies exist; access control and account management policies missing |

**PCI DSS Overall: ❌ Non-Compliant**  
**Critical Gaps:** Requirements 3, 4, 7, 8, 10, 11  
**Potential Penalties:** $5,000–$100,000/month; loss of card processing privileges; mandatory forensic audit post-breach

---

## Part 2 — GDPR Compliance

**GDPR (General Data Protection Regulation)** applies to any organization that processes personal data of EU residents, regardless of where the organization is based.

| Article / Principle | Requirement | Status | Findings |
|--------------------|-------------|--------|----------|
| Art. 5 — Lawfulness | Process data lawfully, fairly, and transparently | ✅ Pass | Privacy policies are documented and enforced |
| Art. 5 — Purpose Limitation | Collect data only for specified, explicit purposes | ✅ Pass | Data collection appears purposeful and documented |
| Art. 5 — Data Minimization | Collect only data that is necessary | ❓ Unverified | Not confirmed in audit scope |
| Art. 5 — Accuracy | Keep personal data accurate and up to date | ❓ Unverified | Not confirmed in audit scope |
| Art. 5 — Storage Limitation | Do not retain data longer than necessary | ⚠️ Partial | Data retention policy exists; enforcement not fully confirmed |
| Art. 5 — Integrity & Confidentiality | Process data with appropriate security (encryption, etc.) | ❌ Fail | No encryption; all employees can access EU customer PII |
| Art. 25 — Data Protection by Design | Implement appropriate technical and organizational measures | ❌ Fail | No least privilege or encryption by design |
| Art. 32 — Security of Processing | Implement appropriate technical safeguards | ❌ Fail | No encryption; no access controls |
| Art. 33 — Breach Notification (72 hrs) | Notify supervisory authority within 72 hours of a breach | ✅ Pass | Breach notification plan is documented |
| Art. 37 — DPO Appointment | Appoint a Data Protection Officer if required | ❓ Unverified | Not confirmed; depends on scale of processing |

**GDPR Overall: ⚠️ Partial Compliance**  
**Strengths:** Breach notification plan in place; privacy policies enforced  
**Critical Gaps:** Articles 5 (Integrity & Confidentiality), 25, 32 — encryption and access controls missing  
**Potential Penalties:** Up to €20 million or 4% of global annual turnover, whichever is higher

---

## Part 3 — SOC 1 / SOC 2 Compliance

**SOC (System and Organization Controls)** reports assess internal controls. SOC 1 focuses on financial reporting controls; SOC 2 assesses the Trust Services Criteria (security, availability, processing integrity, confidentiality, privacy).

### SOC 2 — Trust Services Criteria

| Criteria | Requirement | Status | Findings |
|----------|-------------|--------|----------|
| **Security** — CC6: Logical Access | Restrict logical access to systems and data | ❌ Fail | No least privilege; all users have unrestricted access |
| **Security** — CC6: Authentication | Strong authentication for all users | ❌ Fail | Weak passwords; no MFA |
| **Security** — CC7: Change Management | Manage changes to IT infrastructure | ❓ Unverified | No evidence of formal change management |
| **Availability** — A1 | Maintain availability per commitments | ⚠️ Partial | Systems available, but no DRP — future availability at risk |
| **Confidentiality** — C1 | Identify and maintain confidentiality of data | ❌ Fail | No encryption; unrestricted employee access to confidential data |
| **Processing Integrity** — PI1 | Complete, accurate, valid processing | ✅ Pass | IT has ensured data integrity controls |
| **Privacy** — P1–P8 | Manage personal information per commitments | ⚠️ Partial | Privacy policies exist; access control gaps undermine privacy |

**SOC 2 Overall: ❌ Non-Compliant**  
**Strengths:** Processing integrity controls in place  
**Critical Gaps:** Logical access controls, authentication strength, confidentiality controls

---

## Compliance Summary

| Framework | Status | Key Gaps |
|-----------|--------|----------|
| PCI DSS | ❌ Non-Compliant | Encryption, access controls, IDS, vulnerability management |
| GDPR | ⚠️ Partial | Encryption, access controls (breach notification adequate) |
| SOC 2 | ❌ Non-Compliant | Logical access, authentication, confidentiality |

---

## Recommended Compliance Remediation Steps

### To Achieve PCI DSS Compliance
1. Encrypt all cardholder data at rest (AES-256) and in transit (TLS 1.3)
2. Implement RBAC — restrict cardholder data access to authorized roles only
3. Deploy IDS and enable logging/monitoring for all access to cardholder data
4. Implement strong authentication (MFA) for all users accessing cardholder data
5. Establish a vulnerability management and penetration testing program
6. Complete a PCI DSS Self-Assessment Questionnaire (SAQ) or engage a Qualified Security Assessor (QSA)

### To Achieve Full GDPR Compliance
1. Encrypt all EU customer PII/SPII at rest and in transit
2. Implement least privilege access controls for all personal data
3. Conduct a Data Protection Impact Assessment (DPIA)
4. Review data retention periods and implement automated deletion workflows

### To Achieve SOC 2 Compliance
1. Implement RBAC and enforce least privilege across all systems
2. Enable MFA for all user accounts
3. Document and test a disaster recovery plan to meet availability commitments
4. Establish formal change management procedures
5. Engage a SOC 2 auditor for formal assessment

---

*Compliance checklist prepared as part of the Google Cybersecurity Certificate portfolio.*  
*Botium Toys is a fictional company used for educational purposes.*
