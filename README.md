# Soc2-GRC-capstone
MS Cybersecurity Graduate Capstone — GRC Program Implementation for SOC 2 Type II Readiness

# 🔐 GRC Program Implementation for SOC 2 Type II Readiness
### MS Cybersecurity Graduate Capstone — Western Governors University

> **Simulated enterprise environment:** VyletteTech (fictitious mid-sized SaaS provider)  
> **Platform:** Vanta · AWS · Okta · Splunk · Jira  
> **Timeline:** 10 weeks (January – March 2026)  
> **Budget:** $148,500 | **Status:** ✅ Successfully Completed

---

## 📌 Project Overview

This capstone project documents the **end-to-end design and implementation of a centralized Governance, Risk, and Compliance (GRC) program** aligned with SOC 2 Type II Trust Services Criteria (TSC). The project addressed critical cybersecurity deficiencies in a simulated SaaS environment — fragmented controls, manual evidence workflows, siloed logging, and immature risk management — by deploying a Vanta-based automation platform integrated across the full cloud security stack.

---

## 🚨 Problem Statement

VyletteTech operated without a formal, centralized GRC program, resulting in:

| Deficiency | Impact |
|---|---|
| No centralized control library | 0% formalized TSC mappings (CC1–CC9) |
| Manual, spreadsheet-based risk tracking | 60% of risks had no mitigation plans |
| Fragmented log aggregation | Only ~40% log coverage of critical assets |
| Scattered SOC 2 audit evidence | ~70% of mock evidence requests were incomplete |
| Slow remediation cycles | Average MTTR of 5 days for control-related issues |

These gaps created audit nonconformity risk, undermined incident detection capability, and threatened customer trust and contract renewal in a compliance-sensitive market.

---

## 🛠️ Solution Architecture

A **Vanta-based GRC automation platform** was deployed and integrated with VyletteTech's existing security stack:

```
┌─────────────────────────────────────────────────────────────┐
│                    VANTA GRC PLATFORM                        │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌────────────┐  │
│  │AWS Config│  │Okta SCIM │  │Splunk HEC│  │Jira Webhook│  │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └─────┬──────┘  │
│       │              │              │               │         │
│  Config/Resource  Identity &    Log/SIEM        Remediation  │
│  Baselines        Access Data   Correlation     Workflows    │
│       └──────────────┴──────────────┴───────────────┘        │
│                        Evidence Store                         │
│              (177 SOC 2 TSC Controls Mapped)                  │
└─────────────────────────────────────────────────────────────┘
         ↓                    ↓                   ↓
  Executive Dashboards   GRC Workflows      SecOps Alerts
  (Risk Heatmaps)        (Control Catalog)  (Auto Jira Tickets)
```

### Core Components
- **Vanta** — Central GRC automation platform; system of record for controls, risks, and audit evidence
- **AWS Config** — Cloud configuration baselines and resource inventory
- **Okta SCIM** — Identity & access management events; MFA enforcement monitoring
- **Splunk HEC** — Log aggregation, correlation, and anomaly detection
- **Jira Webhooks** — Automated remediation ticket creation on control failures

---

## 📋 Frameworks & Standards Applied

| Framework | Application |
|---|---|
| **SOC 2 TSC (AICPA 2017)** | Primary compliance target — CC1.1 through CC9.2 mapped in full |
| **NIST CSF v1.1** | Overarching structure: Govern, Identify, Protect, Detect, Respond, Recover |
| **ISO/IEC 27001:2013** | Risk treatment plans, ISMS principles, Annex A control alignment |
| **NIST SP 800-30** | Risk scoring methodology (5×5 matrix, likelihood × impact) |
| **NIST SP 800-50** | Training program design and awareness framework |

---

## 🗂️ Project Phases

| Phase | Duration | Key Deliverable |
|---|---|---|
| 1 — Initiation & Planning | 2 weeks | Signed project charter, Vanta contract, governance model |
| 2 — Assessment & Gap Analysis | 2 weeks | SOC 2 gap analysis, implementation backlog (top 20 gaps) |
| 3 — Design & Architecture | 2 weeks | Integration diagrams, RBAC model, dashboard specs |
| 4 — Implementation | 2 weeks | Live integrations (AWS/Okta/Splunk/Jira), automated monitors |
| 5 — Testing & Validation | 1 week | 50 documented test cases; ≥95% pass rate required |
| 6 — Production Deployment | 3 days | Cutover, hypercare monitoring, dashboard activation |
| 7 — Mock Audit & Closure | 1 week | External mock audit, training handoff, executive sign-off |

**Methodology:** Hybrid Waterfall–Agile (formal governance gates + 2-week Agile sprints)

---

## ✅ Results & Outcomes

### Key Performance Indicators

| KPI | Baseline | Target | Achieved |
|---|---|---|---|
| Evidence Generation Time | 40 hrs/cycle | ≤12 hrs (70% reduction) | ✅ ~70% reduction |
| Mean Time to Remediate (MTTR) | 5 days | <24 hours | ✅ <24 hours |
| Control Monitoring Coverage | ~40% | ≥95% | ✅ 95% |
| Evidence Completeness Score | ~40% | ≥90% | ✅ 96% test pass rate |
| Log Coverage (Critical Assets) | ~40% | >90% | ✅ >90% |

### Testing Summary
- **50 total test cases** executed (30 formative + 20 summative)
- **96% overall pass rate** (exceeds 95% acceptance threshold)
- Integration tests: 20/20 passed (100%)
- Security controls: 10/10 passed (100%)
- Mock audit: **3 minor findings only** — all remediated within 2 weeks

### Operational Impact
- ~120 labor hours saved per audit cycle
- Automated Jira ticket generation eliminated manual alert routing
- MTTD for simulated MFA bypass reduced to <30 minutes

---

## 📁 Deliverables Produced

### Policies & Standards
- SOC 2 Information Security Policy
- Automated Access Review Standard (quarterly, Vanta-driven)
- Centralized Logging & Monitoring Policy (13-month retention)
- Evidence Retention Standard
- Risk Management Procedure

### Technical Documentation
- System Architecture & Data Flow Diagrams (Lucidchart)
- Vanta Configuration & Operations Guide (50-page admin manual)
- Control Mapping Matrix — SOC 2 TSC ↔ NIST CSF ↔ ISO 27001 (177 controls)
- Risk Register & Treatment Plan (50 risks scored and tracked)
- RBAC Model Documentation (20 defined user roles)
- Administrator Runbook with 100+ troubleshooting scenarios

### Original Artifact
**SOC 2 Control Mapping Matrix** — 177-row Excel matrix cross-referencing each SOC 2 TSC control to Vanta automated test ID, control owner, NIST CSF function, ISO 27001 clause, and evidence source.

Sample entry:
```
CC6.1 Logical Access → Vanta Test #142 → GRC Team → PR.AC-1 → A.9.2.2 → Okta SCIM events
CC7.2 Monitoring     → Vanta Test #187 → SecOps   → DE.CM-8 → A.12.4.1 → Splunk HEC
CC9.1 Risk Assess.   → Vanta Test #205 → Exec     → ID.RA-5 → A.6.1.2  → Risk Register
```

---

## ⚠️ Risk Management

10 key risks scored using a 5×5 matrix per NIST SP 800-30 and ISO 31000. Top risks:

| Risk | Score | Level | Mitigation |
|---|---|---|---|
| Integration failures / API changes | 15 | 🔴 High | Early POC, embedded vendor PSM, fallback manual sync |
| Data quality inaccuracies | 16 | 🔴 High | Source validation rules, reconciliation scripts, sampling audits |
| Stakeholder resistance / low adoption | 9 | 🟡 Medium | Champions program, phased rollout, structured training |
| Scope creep | 8 | 🟡 Medium | Change Control Board approval required |

15% budget contingency reserve ($22,250) allocated for R1/R2 mitigation.

---

## 🎓 Skills Demonstrated

`GRC Program Design` `SOC 2 Type II` `NIST CSF` `ISO 27001` `Risk Management`  
`Vanta` `AWS Config` `Okta` `Splunk` `Jira` `SIEM Integration`  
`Evidence Automation` `Control Mapping` `Audit Readiness` `Hybrid Agile PM`  
`RBAC Design` `Security Policy Writing` `KPI Measurement` `Stakeholder Management`

---

## 📚 Key References

- AICPA. (2017). *SOC 2 Trust Services Criteria.* https://www.aicpa.org
- NIST. (2018). *Framework for Improving Critical Infrastructure Cybersecurity v1.1.* https://doi.org/10.6028/NIST.CSWP.04162018
- ISO/IEC. (2013). *ISO/IEC 27001:2013 Information Security Management Systems.*
- Vanta. (2026). *SOC 2 Compliance Automation Implementation Guide.* https://www.vanta.com
- Thoropass. (2024). *Complete 2025 Guide to SOC 2 Gap Analysis.*
- RSI Security. (2025). *How to Conduct a SOC 2 Gap Assessment.*

---

## 👩‍💻 About

**Davina Lauw** | MS Cybersecurity — Western Governors University  
Student ID: 012270262 | Capstone Course: D490  
Submitted: March 2026

---

*This project was completed as a graduate capstone using a fictitious company (VyletteTech). No real proprietary or classified information was used.*
