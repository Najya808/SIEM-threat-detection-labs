# Lab 13: Basic SIEM Dashboards

## Lab Objectives
- Understand the fundamental components and design of Security Information and Event Management (SIEM) dashboards.
- Learn how to create and customize basic SIEM dashboards using open-source tools.
- Gain practical experience in visualizing and interpreting security data.

## Lab Prerequisites
- Basic understanding of network security concepts.
- Familiarity with Linux command-line interface.
- Installed and configured ELK Stack (Elasticsearch, Logstash, Kibana) or any open-source SIEM tool like Wazuh.

## Lab Tasks

### Task 1: Preparing the SIEM Environment
#### 1.1 Verify ELK Stack Installation
- Ensure Elasticsearch, Logstash, and Kibana are up and running.  
- Check their status using:
```bash
sudo systemctl status elasticsearch
sudo systemctl status logstash
sudo systemctl status kibana
1.2 Feed Test Logs into Logstash
Prepare sample log files for ingestion.

Example:

echo "Aug 29 01:00:00 mymachine auth: user root logged in" >> /var/log/auth.log
Configure Logstash to process this data by editing the configuration file at /etc/logstash/conf.d/logstash.conf.

Task 2: Accessing and Setting up Kibana Dashboard
2.1 Access Kibana Interface
Open a web browser and navigate to http://localhost:5601.

Log in with your credentials.

2.2 Navigate to the Dashboard Section
Click on Dashboard from the left panel.

2.3 Create a New Dashboard
Select Create new dashboard.

Click Add a new visualization to start building metrics.

Task 3: Building Basic Visualizations
3.1 Add Log Count Over Time Chart
Select Line chart from the visualization menu.

Set X-axis to @timestamp and Y-axis to count.

Choose an interval like hourly.

Save the visualization as "Log Count Over Time".

3.2 Add Top 5 Source IPs Panel
Choose Data Table visualization.

Set Bucket to Terms and select source.ip for field.

Limit size to 5 to display top 5 IPs.

Save as "Top 5 Source IPs".

3.3 Add Top Event Categories Panel
Select Data Table visualization.

Set Bucket to Terms and select event.category.

Limit size to 5 for top categories.

Save as "Top Event Categories".

Task 4: Finalizing the Dashboard
4.1 Compile Dashboard
Add all created visualizations to the dashboard.

Arrange and resize for optimal layout.

4.2 Save and Share the Dashboard
Save the completed dashboard with a name like "Basic SIEM Overview".

Share the dashboard link with team members or integrate it into SIEM monitoring tools.

Conclusion
In this lab, you have learned how to set up a basic SIEM dashboard using the ELK Stack. You have crafted visual components that offer insights into log data, including log counts over time and top source IPs. These foundational skills in creating and managing dashboards will assist in advanced security data monitoring and management.

What I Learned
How to verify ELK Stack components are running and correctly configured.

How to feed test logs into Logstash for processing.

How to create visualizations like line charts and data tables in Kibana.

How to compile multiple visualizations into a functional dashboard.

The importance of dashboards in monitoring, analyzing, and presenting security data effectively.
