# Miss Shoes — GRC Project (ISO 27001 · SOC 2 · NIST CSF · GDPR)

Frameworks: ISO/IEC 27001 · SOC 2 · NIST CSF · GDPR

Focus: **logging/detections**, **config/change management**, and **privacy rights (DSAR)**.

Data: 100% synthetic (no real PII)

A tangible, audit-friendly project applying GRC controls to a relatable business: a women’s online shoe boutique.

The repo shows end-to-end control execution: policy → procedure/runbook → notebooks/scripts → evidence → one-page reports → crosswalk to frameworks.

---

Table of Contents
- [What to look at first](#what-to-look-at-first)
- [Business processes and assets](#business-processes-and-assets)
- [Mini-projects overview](#mini-projects-overview)
  - [A) Log Review & Detections](#access-review)
  - [B) Configuration & Change Management](#backup--restore-test)
  - [C) Privacy Rights (DSAR)](#data-classification--retention)
- [Repository layout](#repository-layout)
- [Screenshots](#screenshots)

---

## What to look at first 
- `01_case/` — three mini-projects with code, data, logs and reports  
  - **A_Log_Detections/** (Who’s knocking?) 
  - **B_Config_ChangeMgmt/** (Guardrails & drift) 
  - **C_Privacy_DSAR/** (Customer privacy rights)
- `02_Frameworks/` — **Crosswalk_ISO_NIST_SOC2**, **SoA**, **RCM**, **CSF_Assessment**  
- `03_Evidence/hashes/ledger.csv` — integrity index (SHA-256) of key artifacts

> Each mini-project includes **policy**, **procedure/runbook**, **notebook/script**, **evidence**, **KPIs**, and **framework mapping** (ISO 27001 · NIST CSF · SOC 2).

---

## Business processes and assets
- **E-commerce storefront** (orders, payments)  
- **CRM** (customers: names, emails, loyalty)  
- **Inventory system** (shoe SKUs, stock, suppliers)  
- **Payment gateway** (third-party)  
- **Customer support portal** (DSAR intake)

---

## Mini-projects (overview)

### Log Review & Detections — “Who’s knocking?”
**Goal:** Detect suspicious access in web server logs (failed logins, brute force).
**Inputs:** ´data/web_access.log´
**Output:** ´outputs/alerts_evidence.csv´
**Docs/Code:** ´scripts/A_Log_Detections.ipynb´, ´Report_Detections.md´
**KPIs (targets):** 100% logs reviewed weekly · alerts triaged ≤24h · orphan alerts=0
**Frameworks:** ISO 27001 A.8.15/8.16 · NIST CSF DE.CM/DE.AE · SOC 2 CC7.x

### Configuration & Change Management — “Guardrails & drift”

**Goal:** Compare baseline vs. actual system configuration; document changes.
**Inputs:** ´config/baseline.json´, ´config/actual.config´
**Outputs:** ´outputs/config_drift_evidence.csv´
**Docs/Code:** ´scripts/B_Config_ChangeMgmt.ipynb´, ´Change_Ticket.md´, ´Report_ChangeMgmt.md´
**KPIs (targets):** Drift=0 for critical configs · 100% changes documented · review cycle ≤30 days
**Frameworks:** ISO 27001 A.8.9/8.4 · NIST CSF PR.IP/PR.PT · SOC 2 CC7.x

### Privacy Rights (DSAR) — “Customer’s voice”
**Goal:** Fulfill customer DSARs (Data Subject Access Requests) under GDPR.
**Inputs:** ´data/customers.csv´, ´data/dsar_intake.csv´
**Outputs:** DSAR packages (*.zip), evidence logs (´dsar_log_evidence.csv´)
**Docs/Code:** ´scripts/C_Privacy_DSAR.ipynb´, ´DSAR_Procedure.md´, ´Report_DSAR.md´
**KPIs (targets):** 100% DSARs acknowledged ≤1 day · fulfilled ≤30 days · deletions logged with evidence
**Frameworks:** ISO 27001 A.8.10 · NIST CSF PR.DS · SOC 2 Confidentiality/Privacy · GDPR Art. 15-17

---

## Repository layout
<details>
<summary>Click to expand</summary>

  ```
MissShoes/
├─ 01_Case/
│  ├─ A_Log_Detections/
│  │  ├─ data/ # web_access.log
│  │  ├─ outputs/ # alerts_evidence.csv
│  │  └─ scripts/ # A_Log_Detections.ipynb, Report_Detections.md
│  ├─ B_Config_ChangeMgmt/
│  │  ├─ config/ # baseline.json, actual.config
│  │  ├─ outputs/ # config_drift_evidence.csv
│  │  └─ scripts/ # B_Config_ChangeMgmt.ipynb, Change_Ticket.md, Report_ChangeMgmt.md
│  └─ C_Privacy_DSAR/
│     ├─ data/ # customers.csv, dsar_intake.csv
│     ├─ outputs/ # DSAR packages, logs
│     └─ scripts/ # C_Privacy_DSAR.ipynb, DSAR_Procedure.md, Report_DSAR.md
│
├─ 02_Frameworks/
│  ├─ Crosswalk_ISO_NIST_SOC2.csv
│  ├─ CSF_Assessment.xlsx
│  ├─ RCM.xlsx
│  └─ SoA.xlsx
│
├─ 03_Evidence/
│  ├─ Evidence_Builder.ipynb
│  └─ ledger.csv
│
└─ 04_Screenshots/

```
</details>  

---

##  Screenshots

<div style="display: flex; flex-direction: row;">
  <img  style="margin-bottom: 10px;" src="Don Control Pizzas/Captura de pantalla 2025-09-13 233244.png" alt="project" width="350" height="250">
  <img  style="margin-bottom: 10px;" src="Don Control Pizzas/Captura de pantalla 2025-09-13 234052.png" width="350" height="250">


> All datasets are synthetic. No real secrets or PII.
