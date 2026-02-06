---
title: "01-19 debugging maintenance view"
---

### Problem Statement
I’ve set up a Fivetran ingestion pipeline that consolidates these spreadsheets into a single Snowflake table. While this centralizes the data, it introduces duplicate rows, unclear record freshness, and ambiguous state, making the data:

I want to evolve this system into one that is:
1. Trackable — I can reliably answer “what maintenances exist, and what is their current state?”
2. Accurate — no double-counting, no stale records, no accidental fan-out
3. Changeable — easy to update schemas, swap sources, or add new CSPs without breaking downstream analysis

### Steps 
1. Establish a MAINTENANCE_ID as a primary key into the spreadsheets
	1. provider+maintenance_id
2. Reclassify current table as a raw - build views on top of it
3. Create canonical "latest view"
4. Separate ingestion time from event time
	1. DATE_PARTITION / _FIVETRAN_SYNCED → when the system learned
	2. START_DATETIME / END_DATETIME → when the maintenance happened
5. Make the system changeable (future-proofing) 

### System Rules:
- Maintenance_ID = 1 real world maintenance event
### Edge Cases
1. If a CSP does not use spreadsheets (e.g. GCP, CW uses bots) what do i do here? 
2. How do I track maintenances across multiple days? but a low scope each day?
	1. rn each maintenance event is categrorized in a similar amount