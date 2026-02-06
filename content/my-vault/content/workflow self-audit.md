---
title: "workflow self-audit"
---

tools:
- obsidian 
- google calendar
- terminal
- slack
- notion 

workflows i do:
1. maintenance
	1. approve maintenance from csps via 
		1. slack bot 
		2. spreadsheet 
		3. spreadsheet
			1. note: this is scattered and deorganized - how do i make it faster/easier to trigger / input? 
		4. -> fivetran ingestion -> snowflake -> sigma
			1. is there a codex <> snowflake mcp
	2. organize maintenance at go/maintenance 
		1. ingest all cloud providers/internal maintenances
		2. log current fw versions of fleet 
	3. execute maintenance
		1. check cluster / information
			1. ndb -> physical cluster 
				1. if < cluster
					1. cordon / rma nodes via applied
					2. execute applied runbook
	4. comms
		1. if applied
			1. inform scheduling
			2. if >32 nodes 
				1. if >=1 cluster 
					1. run simons script to find engine impact
				2. if ib fabric
					1. run simons script to find affected users 
						1. blast warning and verify ib fabric is ok 
				3. else:
					1. check if important engines 
						1. if important 
							1. cordon nodes <24 pre-maintenance 
							2. trigger resolve 
		2. if research
			1. use @fleet-notifier to inform users 
				1. if broken 
					1. go to zoku -> capacity search -> snapshot users 
				2. else 
					1. deallocate 
					2. execute
				3. track 
					1. maintenance
				4. recover cluster
2. csp work
	1. monitor weekly agendas
	2. monitor feature requests/tracker
		1. monitor cw feature requests 
3. hardware health 
	1. track cluster health 
	2. enforce hardware health sla 
	3. field #.compute support questions
4. meetings
	1. weekly internal
		1. saagar meeting
		2. kenny
		3. hwh on call
		4. hwh general
	2. weekly external
		1. aws
		2. cw 
		3. gcp 
		4. oci
	3. ad-hoc
		1. daniel
		2. eri
general technical skills:
- terminal 
	- running scripts
	- helping with applied on-call
- spreadsheets
	- tracking maintenances 
		- states
			- approved
			- negotiating
			- deferred
			- completed 
		- type 
			- impactful
			- non-impactful
				- <32 nodes
		- csps
			- aws
			- gcp 
			- azure
			- cw
				- cw contracted gcp
				- cw direct
				- cw azure
	- scope
		- cluster id (internal)
		- physical cluster
		- region 
		- num of gpus 
			- raw
			- a100e 
	- impact
		- refer to comms flow above
- snowflake
	- tracking maintenances 
	- backfilling with data from previous maintenances 
	- enforcing invariants 
	- updating based on system 
	- converge towards daniel maintenance conroller 
- random data things
	- "given this csv can you do this to the csv"
	- given this list of nodes can you verify with the other list of nodes 
	- given this physical cluster can u find it in this spreadsheet 
	- can u append clusters from view 1 into view 2 
		- join 
- tracking health of research 
	- go to [cluster health ](https://app.mode.com/openai_tf/reports/c4bd08224a80/runs/3e54a5165576)
	

aspirational workflow:
1. weeklies in google doc 
	1. running task log
		1. timestamped
		2. checkboxes 
	2. spreadsheet
2. dailies 

