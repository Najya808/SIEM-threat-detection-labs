# Lab 21: Searching & Filtering Data

## Objectives
- Understand how to use field-based queries for efficient data searching.
- Learn to filter logs by time range or severity.
- Save frequently used queries for quick access.

## Prerequisites
- Basic understanding of data logs and fields.
- Familiarity with command-line tools.
- Access to Elasticsearch, Kibana, or another open-source SIEM tool.

---

## Introduction
This lab focuses on efficient searching and filtering of log data using field-based queries. These skills help analysts quickly identify important events within large datasets.

---

## Task 1: Utilizing Field-Based Queries

### Example Query
Search logs where source IP starts with 192.168.0:

source.ip:192.168.0.*


### Steps
1. Open your SIEM interface (e.g., Kibana).
2. Enter the query in the search bar.
3. Review results for patterns or anomalies.

---

## Task 2: Filtering Logs by Time Range or Severity

### Example Filter
severity:error


### Steps
1. Set time range to last 24 hours.
2. Apply severity filter.
3. Review filtered logs and visualize if available.

---

## Task 3: Saving a Frequently Used Query

### Steps
1. Execute a useful query.
2. Click Save Query or Bookmark option.
3. Name example:
Error_Logs_Last_24_Hours

4. Access saved queries later for quick analysis.

---

## Conclusion
This lab demonstrated how to search logs using field-based queries, apply time and severity filters, and save frequently used queries. These skills improve efficiency when working with large datasets and enhance incident analysis workflows.
