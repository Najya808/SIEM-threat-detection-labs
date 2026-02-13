# Lab 34: Generating Security Reports

## Objectives
- Learn to generate and interpret security reports.
- Utilize open-source tools to collect and compile security data.
- Export and analyze key security metrics.

## Prerequisites
- Basic understanding of network security concepts.
- Familiarity with command-line tools.
- Installed open-source security tools like OSSEC or Zeek (formerly Bro).

---

## Task 1: Set Up Security Monitoring Tool

### Step 1: Install OSSEC
- Ensure root privileges.
- Update packages:
```bash
sudo apt-get update
Install OSSEC:

sudo apt-get install ossec-hids
Step 2: Configure OSSEC
Edit configuration:

sudo nano /var/ossec/etc/ossec.conf
Define monitoring parameters (e.g., /etc, /var/log directories).

Task 2: Collect Security Event Data
Step 1: Install Zeek (Bro)
sudo apt-get install zeek
Start capturing network traffic:

sudo zeekctl deploy
Step 2: Monitor Logs
Navigate to Zeek logs:

cd /opt/zeek/logs/current
Use cat, less, or more to view .log files.

Task 3: Generate Security Reports
Step 1: Extract Relevant Data
Example: filter critical events:

grep "CRITICAL" /opt/zeek/logs/current/*.log
Step 2: Compile Data into a Report
Use Bash or Python scripts for automation.
Example Bash script:

#!/bin/bash
echo "Security Report Summary"
grep -i "error" /opt/zeek/logs/current/*.log > summary.log
Task 4: Export the Report
Step 1: Convert Report to PDF
pandoc summary.log -o security_report.pdf
Step 2: Convert Report to CSV
Example Python script:

import csv

with open('summary.log', 'r') as infile, open('report.csv', 'w') as outfile:
    writer = csv.writer(outfile)
    for line in infile:
        writer.writerow(line.strip().split())
Conclusion
Learned to monitor network activities using OSSEC and Zeek.

Collected and interpreted security event data.

Generated reports in PDF and CSV formats.

Continuous monitoring and reporting are crucial for maintaining robust network security.
