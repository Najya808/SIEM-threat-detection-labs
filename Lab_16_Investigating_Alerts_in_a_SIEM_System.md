# Lab 16: Investigating Alerts in a SIEM System

## Objectives
- Understand how to locate and interpret alerts in a Security Information and Event Management (SIEM) system.
- Develop the skills to drill down into raw event data associated with an alert.
- Document findings and propose potential next steps for incident response.

## Prerequisites
- Basic understanding of cybersecurity concepts and incident response.
- Familiarity with using a Linux terminal.
- Access to an open-source SIEM platform such as ELK Stack (Elasticsearch, Logstash, Kibana) or Wazuh.
- Basic knowledge of navigating and using a SIEM platform.

---

## Lab Tasks

### Task 1: Locate an Alert in the SIEM

#### Access the SIEM Dashboard
1. Log into your SIEM platform (ELK Stack or Wazuh).
2. Navigate to the **Alerts** section on the dashboard.

#### Identify a Suspicious Login Alert
- Look for alerts categorized under **Security Analytics** or similar.
- Identify alerts such as **Suspicious Login Attempts**, unusual login times, or unknown locations.

#### Filter Alerts
Use filters to narrow down alerts by time, type, or source IP.

Example filter in Kibana:
```json
{
  "query": {
    "bool": {
      "must": [
        { "match": { "alert.category": "suspicious_login" }},
        { "range": { "@timestamp": { "gte": "now-1d/d", "lte": "now/d" }}}
      ]
    }
  }
}
Task 2: Drill Down to Raw Events
Access Raw Event Data
Click on a specific alert to view detailed logs and raw security events.

Analyze the Logs
Look for:

Source IP address

User account involved

Timestamp

Action performed

Login status

Example Log Entry
{
  "timestamp": "2023-10-27T10:32:58Z",
  "source_ip": "192.168.1.100",
  "user": "jdoe",
  "action": "login_attempt",
  "status": "failed"
}
Analysis Tips
Check if the IP is unfamiliar.

Identify repeated failed attempts.

Look for unusual login locations or times.

Task 3: Document Findings and Next Steps
Document Key Findings
Include:

Alert description

Traffic patterns

Suspicious activities

Screenshots or log extracts

Propose Next Steps
Possible actions:

Block suspicious IP addresses

Reset passwords for affected accounts

Increase monitoring for future activity

Example Recommendation:

Based on the suspicious login attempt from IP 192.168.1.100, it is recommended to temporarily block this IP and initiate a password reset for the user jdoe.

Conclusion
In this lab, you learned how to locate and investigate alerts within a SIEM system. You analyzed raw security logs, documented findings, and proposed incident response actions. These skills are essential for proactive cybersecurity monitoring and threat detection.

