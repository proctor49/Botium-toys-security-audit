# IT Asset Inventory — Botium Toys

**Document Type:** Asset Inventory  
**Owner:** IT Department  
**Last Updated:** June 2026  
**Classification:** Internal Use Only

---

## Purpose

This inventory documents all assets managed by the Botium Toys IT Department. Asset classification is a foundational step in the NIST CSF **Identify** function. Understanding what assets exist — and their criticality — is necessary to appropriately prioritize security controls and assess the impact of potential losses.

---

## Asset Classification Definitions

| Classification | Description |
|----------------|-------------|
| **Critical** | Loss would cause immediate, severe business disruption or regulatory violation |
| **High** | Loss would significantly impact operations or customer trust |
| **Medium** | Loss would cause moderate disruption; recovery possible within days |
| **Low** | Loss would cause minor inconvenience; easily replaced |

---

## Section 1 — Hardware Assets

### 1.1 End-User Devices

| Asset | Quantity | Location | Criticality | Notes |
|-------|----------|----------|-------------|-------|
| Desktop Computers | Multiple | Main Office | High | Used for all business operations |
| Laptops | Multiple | Office / Remote | High | Used by remote workers; mobile data risk |
| Smartphones | Multiple | Employee Use | Medium | Company and/or BYOD devices |
| Remote Workstations | Multiple | Remote | High | Requires secure VPN/remote access policies |
| Docking Stations | Multiple | Office | Low | Peripheral; easily replaced |

### 1.2 Peripheral Equipment

| Asset | Quantity | Location | Criticality | Notes |
|-------|----------|----------|-------------|-------|
| Headsets | Multiple | Office | Low | Communication peripherals |
| Keyboards / Mice | Multiple | Office | Low | Standard peripherals |
| Cables / Adapters | Multiple | Office | Low | Infrastructure accessories |

### 1.3 Surveillance Equipment

| Asset | Quantity | Location | Criticality | Notes |
|-------|----------|----------|-------------|-------|
| CCTV Cameras | Multiple | Office, Storefront, Warehouse | High | Physical security deterrent and detective control |

---

## Section 2 — Software & Systems

| System | Purpose | Criticality | Security Notes |
|--------|---------|-------------|----------------|
| **Accounting System** | Financial management and reporting | Critical | Contains financial records; high-value target |
| **E-commerce Platform** | Online sales; processes customer payments | Critical | PCI DSS scope; customer PII/cardholder data |
| **Database (Customer)** | Stores PII, SPII, and cardholder data | Critical | Highest risk — currently unencrypted |
| **Inventory Management** | Tracks storefront and warehouse stock | High | Business operations dependency |
| **Telecommunication System** | Internal and external communications | Medium | Social engineering risk vector |
| **Security Systems** | Access control, monitoring | High | Must remain uncompromised |
| **Antivirus Software** | Malware detection and quarantine | High | Actively monitored; adequate |
| **Firewall** | Network perimeter defense | Critical | Configured with appropriate rules |

---

## Section 3 — Network & Infrastructure

| Asset | Description | Criticality | Security Status |
|-------|-------------|-------------|-----------------|
| **Internal Network** | LAN connecting all office systems | Critical | Firewall in place; no IDS/IPS |
| **Internet Access** | External connectivity for business and e-commerce | Critical | Exposure point for external threats |
| **Data Storage (Local)** | On-premises storage for customer and business data | Critical | Unencrypted; high risk |
| **Data Retention Systems** | Archives and historical data management | High | Retention policy documented |

---

## Section 4 — Physical Assets

| Asset | Location | Criticality | Security Status |
|-------|----------|-------------|-----------------|
| **Main Office** | Company headquarters | High | Locks, CCTV, fire systems in place |
| **Storefront** | Retail customer-facing area | High | Locks, CCTV in place |
| **Warehouse** | Adjacent to storefront; holds product inventory | Medium | Locks, CCTV in place |
| **Retail Inventory (Products)** | Warehouse + storefront | Medium | Physical security adequate |
| **On-Premises Server Hardware** | Main office | Critical | Physical access controls TBC |

---

## Section 5 — Legacy Systems

| System | Status | Monitoring | Risk Level | Notes |
|--------|--------|------------|------------|-------|
| Legacy System(s) (unspecified) | End-of-Life | ⚠️ Informal | 🟠 Medium | Monitored but no formal schedule; no patching from vendor |

> **Recommendation:** Conduct a full legacy system audit to enumerate all end-of-life systems, their network connections, and data access. Prioritize isolation, migration, or decommissioning.

---

## Section 6 — Data Assets

| Data Type | Classification | Storage Location | Encrypted | Access Level |
|-----------|---------------|------------------|-----------|--------------|
| Customer Credit Card Data | 🔴 Critical | Internal Database | ❌ No | All employees (currently) |
| Customer PII (name, address, email) | 🔴 Critical | Internal Database | ❌ No | All employees (currently) |
| Customer SPII (SSN, financial info) | 🔴 Critical | Internal Database | ❌ No | All employees (currently) |
| Employee Records | 🟠 High | Internal Systems | ❓ Unknown | HR + IT (assumed) |
| Financial / Accounting Records | 🟠 High | Accounting System | ❓ Unknown | Finance team |
| Product Inventory Data | 🟢 Low-Medium | Inventory System | N/A | Operations team |

---

## Asset Inventory Gaps & Recommendations

| Gap | Recommendation | Priority |
|-----|---------------|----------|
| Assets not classified by criticality | Conduct formal asset classification workshop | 🟠 High |
| No data flow mapping | Map how cardholder data moves through all systems | 🔴 Critical (PCI DSS) |
| Legacy systems not enumerated | Perform full legacy system discovery | 🟠 High |
| Network gear security unconfirmed | Verify locking cabinets for all network infrastructure | 🟠 Medium |
| No Configuration Management Database (CMDB) | Implement a CMDB to track all assets and configurations | 🟠 Medium |

---

*Asset inventory prepared as part of the Google Cybersecurity Certificate portfolio.*  
*Botium Toys is a fictional company used for educational purposes.*
