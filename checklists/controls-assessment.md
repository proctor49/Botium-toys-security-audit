# Security Controls Assessment Checklist — Botium Toys

**Analyst:** Junior Security Analyst  
**Date:** June 2026  
**Framework Reference:** NIST CSF / Control Categories (Administrative, Technical, Physical)

---

## How to Read This Checklist

| Symbol | Meaning |
|--------|---------|
| ✅ | Control is implemented and adequate |
| ⚠️ | Control exists but is inadequate or incomplete |
| ❌ | Control is not implemented |
| ❓ | Control status could not be verified |

---

## Section 1 — Administrative / Managerial Controls

These controls address the human and policy component of cybersecurity.

| # | Control | Type | Status | Risk if Missing | Notes |
|---|---------|------|--------|----------------|-------|
| 1.1 | **Least Privilege** | Preventative | ❌ | 🔴 High | All employees have unrestricted data access |
| 1.2 | **Separation of Duties** | Preventative | ❌ | 🔴 High | No role separation for high-risk functions |
| 1.3 | **Disaster Recovery Plan** | Corrective | ❌ | 🔴 High | No DRP or BCP documented |
| 1.4 | **Access Control Policy** | Preventative | ❌ | 🔴 High | No formal access control policy exists |
| 1.5 | **Password Policy** | Preventative | ⚠️ | 🟠 Medium | Policy exists but requirements are insufficient |
| 1.6 | **Account Management Policy** | Preventative | ❌ | 🟠 Medium | No defined user lifecycle procedures |

**Section Score: 1 / 6 controls adequately implemented**

---

## Section 2 — Technical Controls

These controls consist of technology-based safeguards.

| # | Control | Type | Status | Risk if Missing | Notes |
|---|---------|------|--------|----------------|-------|
| 2.1 | **Encryption** | Deterrent | ❌ | 🔴 Critical | Credit card data and PII unencrypted at rest and in transit |
| 2.2 | **Data Backups** | Corrective | ❌ | 🔴 High | No backups of any critical data |
| 2.3 | **IDS/IPS** | Detective | ❌ | 🟠 High | No intrusion detection system deployed |
| 2.4 | **Password Management System** | Preventative | ❌ | 🟠 Medium | No centralized enforcement; manual IT resets required |
| 2.5 | **Legacy System Maintenance** | Preventative | ⚠️ | 🟠 Medium | Monitored but no schedule or defined procedures |
| 2.6 | **Firewall** | Preventative | ✅ | N/A | Configured with appropriate security rules |
| 2.7 | **Antivirus (AV) Software** | Corrective | ✅ | N/A | Installed and regularly monitored by IT |

**Section Score: 2 / 7 controls adequately implemented**

---

## Section 3 — Physical Controls

These controls limit physical access to assets and environments.

| # | Control | Type | Status | Risk if Missing | Notes |
|---|---------|------|--------|----------------|-------|
| 3.1 | **CCTV Surveillance** | Preventative / Detective | ✅ | N/A | Up-to-date cameras at all locations |
| 3.2 | **Physical Locks** | Deterrent / Preventative | ✅ | N/A | Sufficient locks on all access points |
| 3.3 | **Fire Detection & Prevention** | Detective / Preventative | ✅ | N/A | Functioning alarms and suppression systems |
| 3.4 | **Locking Cabinets (Network Gear)** | Preventative | ❓ | 🟠 Medium | Not confirmed; should be verified |
| 3.5 | **Time-Controlled Safe** | Deterrent | ❌ | 🟠 Medium | Not implemented |
| 3.6 | **Adequate Lighting** | Deterrent | ❓ | 🟢 Low | Not confirmed in scope documentation |
| 3.7 | **Signage (Alarm Service Provider)** | Deterrent | ❓ | 🟢 Low | Not confirmed |

**Section Score: 3 / 7 controls adequately implemented (2 unverified)**

---

## Summary Scorecard

| Domain | Implemented | Total | Score |
|--------|-------------|-------|-------|
| Administrative Controls | 1 | 6 | 17% ❌ |
| Technical Controls | 2 | 7 | 29% ⚠️ |
| Physical Controls | 3 | 7 | 43% ⚠️ |
| **Overall** | **6** | **20** | **30%** |

> **Interpretation:** Only 30% of evaluated controls are adequately implemented. This aligns with the audit's overall risk score of **8/10 (High)**.

---

## Priority Implementation Order

Based on risk ratings, the following controls should be implemented first:

### 🔴 Immediate (Critical Risk)
1. Encryption — implement AES-256 for data at rest; TLS 1.3 for data in transit
2. Least Privilege + Access Control Policy — role-based access design and enforcement
3. Data Backups — implement 3-2-1 backup strategy with offsite/cloud copy
4. Disaster Recovery Plan — document, test, and maintain a formal DRP/BCP
5. Separation of Duties — enforce for all high-risk transactions and data access

### 🟠 Short-Term (High Risk)
6. IDS/IPS — deploy on internal network with SIEM integration
7. Password Management System — implement centralized tool with MFA
8. Password Policy Update — enforce modern complexity requirements
9. Account Management Policy — define user lifecycle procedures

### 🟡 Medium-Term (Medium Risk)
10. Legacy System Maintenance Schedule — formalize schedule and procedures
11. Locking Cabinets — verify and confirm network gear physical security

---

*Checklist prepared as part of the Google Cybersecurity Certificate portfolio.*  
*Botium Toys is a fictional company used for educational purposes.*
