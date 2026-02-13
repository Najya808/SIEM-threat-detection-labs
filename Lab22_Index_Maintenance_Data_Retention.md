# Lab 22: Index Maintenance & Data Retention

## Objectives
- Understand how to manage index maintenance in data storage systems.
- Learn to configure data retention policies.
- Practice adjusting retention settings to control data lifecycle.
- Verify how the system handles logs past the retention period.

## Prerequisites
- Basic understanding of databases and indexing.
- Familiarity with command-line interfaces.
- Access to an open-source database management system (PostgreSQL or ElasticSearch).
- Installed tools: Python, PostgreSQL/ElasticSearch.

---

## Introduction
This lab focuses on index maintenance and data retention in database systems. Proper management of indexes improves query performance, while retention policies optimize storage and ensure compliance.

---

## Task 1: Understanding Index Maintenance

### Subtask 1.1: Identify Existing Indexes
PostgreSQL example:
```sql
SELECT tablename, indexname, indexdef
FROM pg_indexes
WHERE schemaname = 'public';
Explanation: Lists all indexes in the public schema with table names and definitions.

Subtask 1.2: Analyze Index Usage
PostgreSQL example:

SELECT relname AS table_name,
       indexrelname AS index_name,
       idx_scan AS times_index_used
FROM pg_stat_user_indexes
ORDER BY idx_scan DESC;
Explanation: Shows how often each index is used to identify underused or redundant indexes.

Task 2: Configuring Data Retention
Subtask 2.1: Identify Current Retention Settings
Check your database configuration file (e.g., postgresql.conf).

Review current log or data retention settings.

Subtask 2.2: Adjust Retention Policy
Example:

ALTER DATABASE your_database_name 
SET log_retention = '30 days';
Explanation: Configures the database to retain logs for 30 days.

Task 3: Verify Data Handling Post-Retention Period
Subtask 3.1: Test Retention Policy
Linux cron simulation:

0 0 * * * find /path/to/logs* -mtime +30 -exec rm {} \;
Explanation: Automatically deletes files older than 30 days, simulating retention enforcement.

Conclusion
By completing this lab, you have learned to:

Identify and manage database indexes for optimal performance.

Configure retention policies to automate log lifecycle management.

Test retention settings to ensure obsolete logs are correctly handled.

Proper index maintenance improves query efficiency, while robust retention policies optimize storage and ensure compliance with industry standards.
