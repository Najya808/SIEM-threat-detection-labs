# Lab 32: Backup & Restore of SIEM Data

## Lab Objectives
- Understand backup options and processes available in a Security Information and Event Management (SIEM) system.
- Learn how to perform a manual backup of SIEM data, including indices and rules.
- Simulate a restore process in a test environment to verify data integrity and reliability.

## Prerequisites
- Basic understanding of SIEM systems.
- Access to an open-source SIEM tool (e.g., ELK Stack, Wazuh).
- Admin access to the SIEM environment.
- Basic familiarity with command-line operations.

---

## Lab Tasks

### Task 1: Locate Backup Options in the SIEM

#### 1.1 Access SIEM Management Console
- Log in using administrator credentials.
- Navigate to configuration or management sections for backup options.
- Note: Exact location may vary depending on the SIEM tool.

#### 1.2 Identify Backup Settings
- Look for options related to data management or backups.
- Review documentation to understand features available.

#### 1.3 Understand Retention Policies
- Examine SIEM-defined data retention policies.
- Ensure alignment with organizational requirements.

---

### Task 2: Perform a Manual Backup of Indexes and Rules

#### 2.1 Identify Components for Backup
- Log indices
- SIEM rules and configurations

#### 2.2 Execute Backup Command (Example: ELK Stack)
```bash
curl -X PUT "localhost:9200/_snapshot/my_backup/snapshot_1?wait_for_completion=true" \
     -H 'Content-Type: application/json' -d'{
         "indices": "index_name",
         "ignore_unavailable": true,
         "include_global_state": false
     }'
2.3 Verify Backup Completion
Check SIEM logs or notifications for successful completion.

Confirm backup files exist in the designated storage location.

Task 3: Simulate a Restore in a Test Environment
3.1 Set Up a Test Environment
Prepare a separate test instance of the SIEM system.

Ensure it mirrors production for realistic testing.

3.2 Restore Data from Backup
curl -X POST "localhost:9200/_snapshot/my_backup/snapshot_1/_restore" \
     -H 'Content-Type: application/json' -d'{
         "indices": "index_name",
         "ignore_unavailable": true,
         "include_global_state": false
     }'
3.3 Validate Data Integrity
Compare restored data with original.

Test functionality of restored rules and configurations.

Conclusion
Successfully learned how to backup and restore SIEM data using an open-source approach.

Ensures critical data remains secure and recoverable in case of system failure.

Practicing these procedures in a controlled environment builds confidence and competence for real-world scenarios.
