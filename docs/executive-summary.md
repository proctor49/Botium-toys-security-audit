# Executive Summary — Botium Toys Internal Security Audit

**Prepared by:** Junior Security Analyst  
**Date:** June 2026  
**Classification:** Internal Use Only  
**Audit Scope:** Enterprise-wide security program review

---

## Purpose

This executive summary presents the key findings and recommendations from an internal security audit of Botium Toys' information security program. The audit was conducted in alignment with the **NIST Cybersecurity Framework (CSF)** and evaluated the organization's controls, compliance posture, and overall risk exposure.

---

## Overall Risk Rating

> **Risk Score: 8 / 10 — HIGH**

Botium Toys faces significant security risk due to missing critical controls and non-compliance with regulatory frameworks including **PCI DSS** and **GDPR**. Immediate remediation is required to protect customer data, avoid regulatory fines, and ensure business continuity.

---

## Summary of Findings

The audit identified **11 control gaps** across administrative, technical, and physical domains. The most critical findings are summarized below:

### Critical Issues (Immediate Action Required)

1. **No Data Encryption** — Customer credit card data is stored, processed, and transmitted without encryption, in direct violation of PCI DSS requirements. A breach would expose Botium Toys to significant legal liability and customer trust loss.

2. **Unrestricted Data Access** — All employees can access internally stored data, including sensitive cardholder data and customer PII/SPII. This violates the principle of least privilege and creates an unacceptably large insider threat surface.

3. **No Disaster Recovery Plan** — Botium Toys has no documented disaster recovery or business continuity plan, and no backups of critical data. A single ransomware attack or hardware failure could result in permanent data loss and business interruption.

4. **No Access Controls** — Least privilege and separation of duties have not been implemented. Any employee account, if compromised, could provide full access to all sensitive systems and data.

### Significant Issues (Address Within 30–90 Days)

5. **No Intrusion Detection System** — Without an IDS, the organization cannot detect active intrusions or anomalous activity on its network.

6. **Weak Password Controls** — The existing password policy has minimal complexity requirements. There is no centralized password management system to enforce policy compliance.

7. **Unscheduled Legacy System Maintenance** — End-of-life systems are maintained reactively with no defined schedule or intervention procedures, increasing the risk of unpatched vulnerabilities.

### Adequate Controls (Maintain and Monitor)

- Firewall with appropriate rule sets is in place
- Antivirus software is installed and regularly monitored
- Physical security is adequate (CCTV, locks, fire detection)
- GDPR breach notification procedures are documented
- Privacy policies are enforced among staff

---

## Compliance Status

| Framework | Status | Key Gap |
|-----------|--------|---------|
| PCI DSS | ⚠️ Non-Compliant | No encryption, unrestricted data access |
| GDPR | ⚠️ Partial | 72-hr notification plan exists; access controls missing |
| SOC 1 / SOC 2 | ⚠️ Non-Compliant | Data confidentiality and integrity controls insufficient |

---

## Top Recommendations

| Priority | Action | Impact |
|----------|--------|--------|
| 1 | Implement encryption for all cardholder and PII data at rest and in transit | Reduces breach impact; achieves PCI DSS compliance |
| 2 | Implement least privilege access controls and separation of duties | Reduces insider threat; limits blast radius of any compromise |
| 3 | Develop and test a disaster recovery and business continuity plan | Ensures operational resilience against ransomware and failures |
| 4 | Deploy an Intrusion Detection System (IDS) | Enables real-time threat detection |
| 5 | Implement a centralized password management system with strong policy enforcement | Reduces credential-based attacks |

---

## Next Steps

The IT Department and leadership should review this report and prioritize remediation based on the risk ratings provided in the [Full Audit Report](audit-report.md). A follow-up review is recommended within **90 days** to assess progress against these recommendations.

---

*For full technical details, see the [Complete Audit Report](audit-report.md) and [Risk Assessment](risk-assessment.md).*
