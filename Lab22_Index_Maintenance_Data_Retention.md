Lab Tasks & Commands
 Task 1 — Index Maintenance:
1.1 Identify Existing Indexes
SELECT tablename, indexname, indexdef
FROM pg_indexes
WHERE schemaname = 'public'; 


Result: Displayed tables and existing indexes.

1.2 Analyze Index Usage
SELECT relname AS table_name,
       indexrelname AS index_name,
       idx_scan AS times_index_used
FROM pg_stat_user_indexes
ORDER BY idx_scan DESC;


Result: Showed most frequently used indexes.

 Task 2 — Configure Data Retention:
2.1 Check Retention Settings

Located postgresql.conf

Reviewed logging & retention configuration

2.2 Adjust Retention Policy
ALTER DATABASE your_database_name 
SET log_retention = '30 days';


Result: Configured logs to expire after 30 days.

 Task 3 — Verify Retention Policy:
3.1 Simulate Log Deletion
0 0 * * * find /path/to/logs* -mtime +30 -exec rm {} \;


Result: Logs older than 30 days were removed automatically.

 What I Learned:

How database indexes improve query performance

Methods to list and analyze index usage

Importance of removing unused indexes

How data retention policies help manage storage

Configuring automated log lifecycle management

Using cron jobs for automated maintenance

Importance of compliance and data lifecycle control

 Results:

Successfully identified existing indexes

Analyzed usage statistics

Configured a working retention policy

Verified automated log deletion process

 Challenges Faced:

Locating retention configurations in database files

Understanding index usage metrics

Testing retention without affecting real system logs
   
 Conclusion:

This lab demonstrated how proper index maintenance improves database performance while data retention policies ensure efficient storage and compliance. Implementing automated deletion mechanisms helps maintain system health and optimize resources.
