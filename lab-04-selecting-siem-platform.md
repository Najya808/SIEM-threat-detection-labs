# Lab 04 — Selecting a SIEM Platform

## Lab Overview
This lab focused on understanding different SIEM platforms, comparing open-source and commercial solutions, and deploying the Elastic Stack (ELK) in a lab environment to simulate SIEM functionality.

---

## Objectives
- Understand SIEM platform fundamentals
- Compare open-source vs commercial SIEM solutions
- Evaluate SIEM tools based on cost, scalability, complexity, and support
- Deploy Elastic Stack as a SIEM platform in a lab

---

## Tools & Technologies
- Elastic Stack (Elasticsearch, Logstash, Kibana)
- Wazuh
- Linux CLI
- Virtual Machine Environment
- OpenJDK 11

---

## Task 1 — Identify SIEM Platform Options

### Open Source SIEM
- Elastic Stack (ELK)
- Wazuh

### Commercial SIEM
- Splunk
- IBM QRadar

---

## Task 2 — Evaluate SIEM Platforms

### Evaluation Factors
- Cost
- Complexity
- Scalability
- Support

### Example Evaluation

**Elastic Stack**
- Pros: Highly scalable, customizable, no licensing cost
- Cons: Complex setup, requires maintenance

**Wazuh**
- Pros: Security-focused, strong community
- Cons: May require additional integrations

---

## Task 3 — Install Elastic Stack

### Update System
```bash
sudo apt-get update && sudo apt-get upgrade
Install Java
sudo apt-get install openjdk-11-jdk
Install Elasticsearch
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo sh -c 'echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" > /etc/apt/sources.list.d/elastic-7.x.list'
sudo apt-get update
sudo apt-get install elasticsearch
Edit configuration:

/etc/elasticsearch/elasticsearch.yml
Start service:

sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
Install Logstash
sudo apt-get install logstash
Example config:

/etc/logstash/conf.d/logstash.conf
input {
  beats {
    port => "5044"
  }
}
filter {
  grok {
    match => { "message" => "%{COMBINEDAPACHELOG}" }
  }
}
output {
  elasticsearch {
    hosts => ["localhost:9200"]
  }
}
Start service:

sudo systemctl start logstash
sudo systemctl enable logstash
Install Kibana
sudo apt-get install kibana
Edit config:

/etc/kibana/kibana.yml
Start service:

sudo systemctl start kibana
sudo systemctl enable kibana

Key Concepts Learned:
SIEM platform comparison and evaluation

Elastic Stack deployment

Log ingestion and processing pipeline

SIEM architecture basics
