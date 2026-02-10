# Lab 01 — Introduction to SIEM (Wazuh)

## Lab Overview

This lab introduces the fundamentals of Security Information and Event Management (SIEM) and demonstrates how to deploy and configure an open-source SIEM solution (Wazuh) for monitoring and alerting.

---

## Objectives

- Understand what SIEM is and its role in cybersecurity
- Learn about log collection, correlation, and alerting
- Deploy an open-source SIEM solution
- Explore SIEM use cases in small environments such as a Homeowners Association (HOA)

---

## Prerequisites

- Basic networking and cybersecurity knowledge
- Familiarity with Linux command line
- Virtual machine or cloud lab environment
- Docker installed

---

## Key Concepts

### Log Collection
Gathering logs from systems like servers, firewalls, and web services for monitoring.

### Correlation
Connecting multiple log events to detect suspicious behavior or attacks.

### Alerting
Generating automated notifications when security rules are triggered.

---

## Tools Used

- Wazuh (Open Source SIEM)
- Docker
- Linux

---

## Lab Tasks

---

### Task 1 — Deploy Wazuh SIEM

**Run Wazuh using Docker**

```bash
docker run -d --name wazuh -p 55000:55000 -p 1514:1514/udp -p 514:514/udp -e NETWORK_MODE=host wazuh/wazuh
Verify Container Status

docker ps
Task 2 — Log Collection
Configured Wazuh to collect logs from:

Web server

Firewall

Modified configuration file:

/var/ossec/etc/ossec.conf
Verify Logs

tail -f /var/ossec/logs/ossec.log
Task 3 — Log Correlation
Created custom rule file:

custom_rules.xml
Sample Rule

<group name="custom">
  <rule id="100001" level="10">
    <decoded_as>json</decoded_as>
    <field name="action">login</field>
    <field name="status">failure</field>
    <description>Failed login attempt detected</description>
  </rule>
</group>
Simulated failed login attempts to trigger correlation rules.

Task 4 — Alerting
Configured alerting via:

Wazuh dashboard

Email or web notifications

Tested alerts by triggering security rule violations.

HOA Use Case
A SIEM solution like Wazuh can help HOAs monitor:

Unauthorized Wi-Fi access

Shared resource misuse

Suspicious login activity

Real-time alerts help improve overall community network security.

What I Learned
SIEM collects and analyzes logs from multiple sources

Correlation rules help detect attack patterns

Alerting enables proactive security monitoring

Wazuh provides centralized security visibility

Conclusion
This lab demonstrated how SIEM platforms enhance cybersecurity through monitoring, correlation, and alerting. Deploying Wazuh provided hands-on experience with real-world security operations applicable to both enterprise and small environments.
