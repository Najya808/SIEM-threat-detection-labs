# Lab 05 — Installing Your Chosen SIEM (ELK Stack)

## Lab Overview
This lab covers the installation and basic configuration of an open-source Security Information and Event Management (SIEM) system using the ELK Stack (Elasticsearch, Logstash, Kibana).  
By the end, you will have a functioning SIEM capable of collecting and visualizing log data.

---

## Objectives
- Understand basic SIEM installation procedures
- Configure Elasticsearch, Kibana, and Logstash
- Verify SIEM services are running

---

## Prerequisites
- Linux system (Ubuntu Server/CentOS)
- Minimum 4GB RAM and 20GB disk space
- Internet access
- Superuser privileges

---

## Tools & Technologies
- ELK Stack (Elasticsearch, Logstash, Kibana)
- Linux CLI
- wget, curl, nano

---

## Task 1 — Preparation and Setup

### System Update
```bash
sudo apt update && sudo apt upgrade -y
Install Dependencies
sudo apt install openjdk-11-jdk -y

Task 2 — Installing Elasticsearch
Download and Install
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.8.0-amd64.deb
sudo dpkg -i elasticsearch-8.8.0-amd64.deb
Configure Elasticsearch
Edit /etc/elasticsearch/elasticsearch.yml:

cluster.name: myELKCluster
network.host: localhost
Start and Enable Service
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch

Task 3 — Installing Kibana
Download and Install
wget https://artifacts.elastic.co/downloads/kibana/kibana-8.8.0-amd64.deb
sudo dpkg -i kibana-8.8.0-amd64.deb
Configure Kibana
Edit /etc/kibana/kibana.yml:

server.host: "localhost"
elasticsearch.hosts: ["http://localhost:9200"]
Start and Enable Service
sudo systemctl start kibana
sudo systemctl enable kibana

Task 4 — Installing Logstash
Download and Install
wget https://artifacts.elastic.co/downloads/logstash/logstash-8.8.0-amd64.deb
sudo dpkg -i logstash-8.8.0-amd64.deb

Task 5 — Verification
Verify Elasticsearch
curl -X GET "localhost:9200/"
Verify Kibana
Open in browser: http://localhost:5601

Conclusion
You have successfully installed and configured a basic SIEM environment using the ELK Stack. Your system is ready to collect, process, and visualize logs for security monitoring.

Key Concepts

SIEM: Security Information and Event Management

ELK Stack: Elasticsearch + Logstash + Kibana

Elasticsearch: Data search and analytics engine

Kibana: Visualization tool

Logstash: Data collection and processing
