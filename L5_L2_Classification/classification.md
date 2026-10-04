# L5 Narrow / L2 General Classification — sovereign-os-deployment
**Platform:** Anticloud | **PAX:** 27B | **IP:** USPTO pending 2026, Anticloud FZ LLE
**Domain:** Deployment automation for SOVEREIGN_OS: ansible-based hardening across fleet

## L5 Narrow
sovereign-os-deployment specializes in deployment automation for sovereign_os: ansible-based hardening across fleet within the Anticloud sovereign deployment boundary. All operations stay local — no cloud services, no external APIs, no data exfiltration. The narrow scope ensures deterministic, auditable behavior that PAX 27B can reason about precisely.

## L2 General
L2 General means sovereign-os-deployment is available to all 9 Anticloud tiers without per-tier configuration. The same API serves hospital, defense, robotics, and research deployments.

## PAX Integration
PAX 27B validates Ansible playbooks before execution: checks for insecure configurations, missing AIOSS chain setup, or incorrect GPU cgroup allocation.

## AIOSS Audit Relevance
Every deployment event (host + hardening profile hash + before-state hash + after-state hash + compliance score) is AIOSS-chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Tamper-evident, offline-verifiable, zero cloud dependency.

## Regulatory / Compliance
NIST SP 800-53 CM-7 (least functionality), CIS Benchmark
