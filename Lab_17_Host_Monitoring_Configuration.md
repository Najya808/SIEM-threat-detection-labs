# Lab 17: Host Monitoring Configuration

## Objectives
- Install a host intrusion detection agent.
- Enable active monitoring for file changes and suspicious processes.
- Verify alerts are appropriately populated in the SIEM system.

## Prerequisites
- Basic knowledge of Linux command line operations.
- Familiarity with SIEM concepts and terminology.
- Access to a Linux-based environment (preferably Ubuntu).
- Access to an open-source SIEM system for alert verification.

---

## Task 1: Install Host Intrusion Detection Agent

### Introduction
Host-based Intrusion Detection Systems (HIDS) monitor internal system activities such as logs, file changes, and processes.  
Examples include **OSSEC** and **Wazuh**.

### Installation Steps

#### Install OSSEC
```bash
sudo apt-get update
sudo apt-get install wget
wget -U ossec https://updates.atomicorp.com/installers/ossec-installer.sh
sudo sh ossec-installer.sh
Configure OSSEC
Choose local installation.

Enable log monitoring and rootkit detection.

Verify Installation
sudo systemctl status ossec
Task 2: Enable Active Monitoring
File Integrity Monitoring
Edit configuration file:

sudo nano /var/ossec/etc/ossec.conf
Add:

<syscheck>
   <directories check_all="yes">/etc,/usr/bin,/var/www</directories>
</syscheck>
Save and exit.

Monitor Suspicious Processes
Edit rules file:

sudo nano /var/ossec/rules/local_rules.xml
Add:

<group name="my_custom_rules">
   <rule id="100100" level="10">
      <decoded_as>process_failed</decoded_as>
      <description>Potential malicious activity detected!</description>
   </rule>
</group>
Restart OSSEC:

sudo systemctl restart ossec
Task 3: Confirm Alerts in SIEM
Simulate an Event
sudo touch /etc/monitored_file
Verify in SIEM
Log into your SIEM dashboard.

Navigate to Alerts or Security Events.

Confirm that the alert appears.

Conclusion
In this lab, you installed a host-based intrusion detection system, configured active monitoring, and verified alerts inside a SIEM platform. This improves early threat detection and strengthens host-level security monitoring.
