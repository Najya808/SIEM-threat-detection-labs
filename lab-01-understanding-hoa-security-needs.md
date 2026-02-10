# Lab 02 — Understanding HOA Security Needs

## Lab Overview
This lab focused on identifying the cybersecurity requirements of a Home Owners Association (HOA) environment.  
The goal was to identify assets, analyze threats, and define initial security objectives.

---

## Objectives
- Identify HOA assets and sensitive data
- Understand threats and vulnerabilities
- Define initial HOA security goals

---

## Tools & Technologies
- OWASP Threat Dragon
- OpenVAS
- Linux CLI
- Threat Modeling Concepts

---

## Task 1 — Identify HOA Assets

### Assets Identified
- Resident Information (PII)
- CCTV Logs
- Financial Records
- HOA Operational Data

### Data Classification
- Sensitive Data → Resident Information
- Operational Data → CCTV & Meeting Notes

---

## Task 2 — Threats & Vulnerabilities

### Threat Modeling Tool
OWASP Threat Dragon

```bash
sudo apt update
sudo apt install snapd
sudo snap install threat-dragon
Vulnerability Scanning Tool
OpenVAS

sudo apt install openvas
sudo greenbone-feed-sync
sudo gvm-setup
Threat Examples
Unauthorized Access

Data Breaches

Physical Security Risks

Task 3 — Security Goals
Protect Resident Privacy

Maintain Data Integrity

Restrict Unauthorized Access

Create Incident Response Plan

Example Policy
Encrypt CCTV footage

Limit access to authorized personnel

Key Concepts Learned
Asset Identification

Threat Modeling

Vulnerability Assessment

Security Policy Design

