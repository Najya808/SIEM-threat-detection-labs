# Lab 36: Onboarding a New Log Source

## Lab Objectives
- Understand the process of onboarding a new log source into a SIEM system.
- Learn to install and configure a log collector or agent.
- Validate and parse incoming logs effectively.

## Prerequisites
- Basic understanding of SIEM systems and architecture.
- Familiarity with command-line interfaces.
- Access to a cloud application or IoT device for integration.
- Installed and configured open-source SIEM system (e.g., Wazuh, Graylog).

---

## Task 1: Select a New Source
### Example Sources
- **Cloud Applications:** AWS CloudWatch, Google Cloud Logging  
- **IoT Devices:** Raspberry Pi, Arduino-based device  

### Steps
1. Identify a source relevant to your operational environment.
2. Ensure the source generates logs compatible with your SIEM system.

---

## Task 2: Install/Configure a Collector or Agent

### Step 1: Select an Open-Source Agent/Collector
- **Wazuh:** Use `ossec-agent`  
- **Graylog:** Use `beats` or `nxlog`

### Step 2: Installation and Configuration Example (Wazuh)
```bash
sudo apt-get update
sudo apt-get install wazuh-agent
Step 3: Configure the Agent
Edit the configuration file:
/var/ossec/etc/ossec.conf

Specify:

Server IP

Log collection details

Step 4: Start and Enable the Agent
sudo systemctl start wazuh-agent
sudo systemctl enable wazuh-agent
Task 3: Validate and Parse Logs in SIEM
Step 1: Check Log Transmission
Ensure logs from the new source are being received in the SIEM.

Verify in Wazuh:

tail -f /var/ossec/logs/ossec.log
Step 2: Parse Logs
Create parsing rules if necessary to extract meaningful information.

Example JSON Field Extraction:

{
  "key": "value",
  "timestamp": "2023-10-16T08:55:00Z"
}
Step 3: Validate Parsed Data
Confirm that parsed information is reflected in the SIEM dashboard.

Check that alerts and patterns match expected outcomes.

Key Concepts
Collector/Agent: Gathers logs from various sources and forwards them to a centralized SIEM.

Log Parsing: Converts raw log entries into structured, analyzable data.

SIEM Integration: Connecting external sources to a SIEM for centralized monitoring and threat detection.

Case Study Example
Scenario: A medium-sized enterprise integrates AWS CloudWatch logs into Graylog to centralize monitoring and improve threat detection.

Challenge: Ensuring seamless integration under high load.

Approach: Used awsbeats plugin for efficient log collection and parsing.

Conclusion
Successfully onboarding a new log source involves:

Selecting the right source.

Installing or configuring a collector/agent.

Validating and parsing logs in the SIEM.

Following these steps enhances security visibility and improves the organization’s ability to detect and respond to incidents effectively.

