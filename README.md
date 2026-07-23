# NIST CSF 2.0 Control Mapping — Home Lab

Mapping 18 NIST Cybersecurity Framework (CSF) 2.0 subcategories to technical controls implemented in a personal home lab, with screenshot evidence and a scored maturity assessment.

## Objective

Most GRC portfolio projects stop at "I know the framework." This one ties every mapped subcategory to something observable and screenshot-verifiable in a real environment — a Wazuh SIEM and a pfSense firewall — and scores current maturity honestly, including the gaps.

## Environment

| Component | Details |
|---|---|
| SIEM | Wazuh 4.14.6 |
| Monitored endpoint | Windows 10 Pro (DESKTOP-E4J3CS6) |
| Firewall | pfSense Community Edition 2.8.1 |
| Framework | NIST CSF 2.0 (published Feb 26, 2024) |

## Methodology

1. Selected 18 CSF 2.0 subcategories spanning all six Functions (Govern, Identify, Protect, Detect, Respond, Recover) that are testable against a home lab.
2. For each subcategory, identified the specific lab control that satisfies (or fails to satisfy) it — e.g. `PR.AA-05` → pfSense WAN firewall rules enforcing default-deny inbound.
3. Captured screenshot evidence for every mapped control (see `/evidence`).
4. Scored current maturity on a 0–4 scale (Not Performed → Optimized) and documented the specific gap where maturity was below "Managed."

## Key Results

- **Overall average maturity: 1.83 / 4** across the 18 mapped subcategories
- **Protect** scored highest (avg. 2.71) — deny-by-default firewall policy and current patch levels are strong, verifiable controls
- **Govern, Respond, and Recover** scored 0 — no written policy, incident response plan, or backup/recovery process currently exists. These are included deliberately (not omitted) with a recommended next step for each, because a credible maturity assessment reports gaps as clearly as it reports strengths.
- Biggest identified gap: pfSense (network-layer) logs are not yet forwarded into Wazuh, so detection and correlation are currently limited to the single Windows endpoint rather than combined network + host visibility.

## Files in This Repository

```
nist-csf-control-mapping-homelab/
├── README.md
├── CSF_Control_Mapping.xlsx      # Full mapping, maturity scoring, and gap analysis
└── evidence/                     # 10 screenshots referenced in the mapping
    ├── EV01_wazuh_agents_inventory.jpg
    ├── EV02_pfsense_package_manager.jpg
    ├── EV03_wazuh_overview_dashboard.jpg
    ├── EV04_wazuh_sca_cis_benchmark.jpg
    ├── EV05_pfsense_user_manager.jpg
    ├── EV06_pfsense_wan_firewall_rules.jpg
    ├── EV07_pfsense_system_update.jpg
    ├── EV08_pfsense_wan_interface_config.jpg
    ├── EV09_wazuh_threat_hunting_dashboard.jpg
    └── EV10_wazuh_mitre_attck_dashboard.jpg
```

**`CSF_Control_Mapping.xlsx` contains four tabs:**
- `Read Me` — scope and maturity rating scale
- `Control Mapping` — the 18 subcategory-to-control mappings with evidence and scores
- `Maturity Summary` — roll-up by CSF Function with a chart, plus a prioritized gap/remediation list
- `Evidence Index` — cross-reference of each screenshot to the subcategories it supports

## Skills Demonstrated

- NIST CSF 2.0 framework fluency (Functions, Categories, Subcategories)
- Control-to-outcome mapping methodology
- Maturity model scoring and gap analysis
- SIEM operations (Wazuh: agent management, SCA/CIS benchmarking, MITRE ATT&CK-based detection, threat hunting)
- Firewall administration (pfSense: rule base design, least privilege, patch/version management)
- GRC documentation and evidence management

## About

This project is part of an ongoing home-lab and portfolio-building track supporting a transition into entry-level GRC / IT Risk / Compliance Analyst roles. Related work includes ISO 27701 privacy gap analysis, SIEM-based threat detection labs, and an ISO 27001/NIST CSF-mapped Information Security Policy Suite.

**Connect:** [LinkedIn] · [GitHub]
