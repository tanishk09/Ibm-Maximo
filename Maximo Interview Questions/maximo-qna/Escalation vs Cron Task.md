# Maximo Interview Q&A – Escalation vs Cron Task

---

## Question 1: Can you explain the difference between Escalation and Cron Task in IBM Maximo?

**Answer:**

- **Escalation**  
  - Used to monitor application records based on **conditions** (via SQL where clause).  
  - Triggers actions when records meet the criteria.  
  - Common uses: SLA deadline monitoring, overdue work orders, auto status change, sending notifications, or invoking workflows.  

---

- **Cron Task**  
  - A **time-based scheduler** that runs system jobs at defined intervals.  
  - Configured in the **Cron Task Setup** application.  
  - Often linked to Java classes or automation scripts.  
  - Common uses: data synchronization, PM generation, background data cleanup, sending scheduled reports, etc.  

---

## Question 2 (Scenario-based):  
👉 *If we have a Cron Task scheduled to run every 5 minutes, but the server goes down for 30 minutes, when the server comes back up will the Cron Task process the missed records?*

**Answer:**

- **Default behavior:** Cron tasks are time-based. If the server is down at the scheduled run time, those executions are **skipped**. They do not automatically catch up after restart.  

- **Custom behavior (if coded):**  
  - If the Java class or automation script linked to the Cron Task is written to check timestamps (e.g., "last run date"), it can identify missed records and process them after the server is back.  
  - This means the outcome depends on how the Cron logic is implemented.  

✅ **Key takeaway:** By default, Cron tasks do **not** retroactively run missed jobs. To handle gaps, custom logic must be added.

---
