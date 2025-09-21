# Configuration & Change Management — Report

**Scope:** Web front security config (nginx-like)
**Objective:** Detect and remediate config drift against a security baseline.

## KPIs 
- 100% changes with approvals & rollback plan
- 0 critical drifts in production
- Mean time to remediate drift (MTRD) ≤ 7 days

## Current Results
- Drift report: see `outputs/config_drift.csv`
- Notable gaps: TLSv1/1.1 enabled; HSTS missing; CSP too permissive; rate limit disabled

## Actions
- Apply CHG ticket to enforce TLS1.2+, set HSTS, tighten CSP, enable rate limit

## Evidence Map
- Baseline: `config/baseline.json` 
- Actual: `config/actual.conf`
- Drift: `outputs/config_drift.csv`

## Framework Mapping
- ISO/IEC 27001: A.8.9, A.8.4
- NIST CSF: PR.IP / PR.PT
- SOC 2: CC7.1 / CC7.4

*Used: moz://a SSL Configuration Generator*
