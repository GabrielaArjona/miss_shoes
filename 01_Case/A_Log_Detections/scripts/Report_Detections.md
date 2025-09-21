# Log Detections — Report

**Period reviewed:** last 7 days  
**Sources:** Apache/Nginx access log (synthetic)  
**Objective:** Detect anomalies (brute force, traversal, SQLi, admin probing) and triage within SLA.

## KPI
- Coverage: 100% of defined log sources reviewed weekly
- MTTD: ≤ 1 hour for High severity
- Triage: ≥ 95% alerts triaged within 24h
- False positive rate: ≤ 5%

## Current Results
- Alerts generated: see `outputs/alerts.csv`
- High: 15, Medium: 37
- Status: triage in progress; actions below

## Actions
- Block offending IP ranges; enable WAF rules for traversal/SQLi; rate-limit auth endpoints.

## Evidence Map
- Log: `data/web_access.log`
- Alerts: `outputs/alerts.csv` (signed in evidence ledger)

## Framework Mapping
- ISO/IEC 27001: A.8.15 Logging, A.8.16 Monitoring
- NIST CSF: DE.CM / DE.AE
- SOC 2: CC7.2/CC7.3
