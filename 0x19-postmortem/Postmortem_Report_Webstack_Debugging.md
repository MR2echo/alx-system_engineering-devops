# Postmortem Report

### Issue Summary:

**Duration:** -  May 10, 2024, 08:00 UTC to May 11, 2024, 03:00 UTC
**Impact:** - The web application experienced intermittent downtime, resulting in slow response times and sporadic errors. Approximately 30% of users were affected by service disruptions.
**Root Cause:** - A database connection pool exhaustion due to misconfigured connection settings.

###Timeline:

**May 10, 2024, 08:30 UTC:** - Issue detected via monitoring alerts indicating increased error rates and latency.
**May 10, 2024, 08:35 UTC:** - Engineering team initiated investigation into potential causes, focusing on database performance and network connectivity.
**May 10, 2024, 09:15 UTC:** - Initial assumption made that the issue was related to a recent deployment, prompting a rollback.
**May 10, 2024, 10:00 UTC:** - Rollback did not resolve the issue. Attention shifted to database performance metrics.
**May 10, 2024, 11:30 UTC:** - Misleading investigation into network infrastructure, leading to no significant findings.
**May 10, 2024, 12:45 UTC:** - Incident escalated to senior database administrators for further analysis.
**May 10, 2024, 14:00 UTC:** - Database administrators identified the root cause as a misconfigured database connection pool.
**May 11, 2024, 02:00 UTC:** - Resolution implemented by adjusting database connection pool settings and restarting affected services.

###Root Cause and Resolution:

**Root Cause:** - The misconfigured database connection pool settings led to an exhaustion of available connections, causing the web application to experience intermittent downtime.
**Resolution:** - Database connection pool settings were adjusted to ensure an adequate number of connections were available. Additionally, affected services were restarted to apply the configuration changes.

###Corrective and Preventative Measures:
**Improvements/Fixes:
**Tasks to Address the Issue:

 -- By implementing these measures, we aim to minimize the risk of similar outages in the future and maintain a high level of service availability for our users.
