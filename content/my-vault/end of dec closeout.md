---
title: "end of dec closeout"
---

### 

1. **Maintenance** 
	1. #.fleet-team
    2. where people can go to find the maintenance schedules for the next [N] weeks / months with a runbook + plans to scale it up / make it better
    3. Slow Maintenance
    4. Generic Operations Doc
2. **Overallocation**
    1. Overallocation update would just be in [#.fleet-team](https://openai.enterprise.slack.com/archives/C0884QEUEAZ) / [#.hardware-health](https://openai.enterprise.slack.com/archives/C041F28TN8K) similar to Carpus' messaging in [compute-rs](https://openai.enterprise.slack.com/archives/C081G0L717A) articulating delays and how we're going to work on getting this done in early-Jan.
    2. #prj-overallocation 
    hey folks wanted to give an update on our overallocation efforts here!

    Last week: published announcement on overallocation as a common pattern in #research-ah-announcements [here](https://oai-research-ah.slack.com/archives/C07CJT8J1H6/p1765299623870239)
    
    Next week: @.carpus will share proposed plan for allocations with RPMs before holiday break (this will reflect the >=85% SLAs, based on historical health of the cluster)
    
    Early Jan: New compute shuffle will be implementing. On Zoku allocations will be set higher than the ≥85% SLA, so researchers can benefit from extra healthy capacity. HWH team will restore clusters that fall below their “planned” SLA.
    
    thanks to @shantanu @jos @angelafan
    
    3. #fleet-team

    4. #hardware-health
`Thanks @channel for your patience and understanding with the rescheduling.

We have worked with RPMs to reflect hardware health SLA's into the next compute planning cycle. Once we get back from break in Jan, the RPM team (@carpus) will implement the new allocations in order to reflect a buffer for hardware health. From there, users will see an adjusted number on Zoku that reflects a more realistic state of the fleet health. 

*Example RPM Post*

`**Overallocation Adjustments Deferred Until after Holiday Break**

`Thanks @channel for your patience and understanding with the rescheduling;We'll be working through the compute allocations with Mark and Jakub next week and plan to share the proposed plan before the holiday break.

To minimize disruption right before the holidays, we’ll wait until **after the break** to implement the shuffle. We really appreciate the flexibility as we work to land this cleanly. (edited)

hey folks wanted to give an update on our overallocation efforts 
Last week we announced to #research-ah-announcements 1) overallocation as a problem and 2) our plan to adjust allocations 3) support from hwh for out-of-SLA clusters here.

For our next compute cycle, RPMs will plan against the HWH SLAs of our clusters (85% min, 90-95% for historically healthy clusters / big run clusters). RPMs will help us share the expectations for hardware health with their teams. 

New Zoku allocations will land in January post-break (@carpus). Users will see numbers with a slight buffer to allow for hardware health events, as well as target healthy nodes  and billable nodes that reflect the HWH SLA and the total number of nodes-per-island (sourcing directly from ndb, ty @leochen!)  Zoku allocations will be set higher than the number RPMs plan against - so users can benefit from extra healthy nodes. Any healthy nodes above the Zoku allocation can be used as flex
(@jos). For future #.compute-support requests, HWH team will keep clusters above the planned SLA, but for questions about extra nodes above SLA please point them to our overallocation explanation (. For clusters out of SLA we'll track via sev. 

Appreciate the feedback from everyone - @shantanu @jos @natan @leochen @mengqingw @angelafan @carpus @kenny @saagarp - and there's definitely more to consider in terms of tracking our HWH SLAs or increasing the buffer we provide on Zoku. We'll iterate the numbers based on feedback from next compute cycle.



Unified Maintenance 


Unified-maintenance view - We've consolidated all our maintenances (5 spreadsheets across CSPs) into one Sigma table view on go/maintenances. Here you can find maintenance schedules for the next 2 months (as well as prev maintenances for the curious). After break, the upcoming week's schedule will be exported to #.fleet-scheduled-maintenance every Mon.
(ty @.cristian for helping w the data plumbing on this one)

Calendar - The calendar will be updated for maintenances within the next 1 - 3 weeks. 

Notifications - For full-cluster maintenance on research clusters, we give tenants/RPM 2w+ notice, via #.compute-rs,  #.rpm-computers, @Fleet-Notifier. For full-cluster maintenance on applied clusters, we give scheduling team 2w+ notice. 
For low-impact maintenance on applied clusters (<32 nodes or IB switches) we will give scheduling team ~3 - 5 days notice, as will check with users if IB workloads will be impacted.
(exceptions for break-fix maintenances aka it's worse to delay maintenance than to take it)

What's coming down the pipe come Jan - March:
- Gradual maintenances with a first trial on GCP B200s - c263 will start with <32 nodes a day on ~January 13 - see [Rolling Maintenance](https://docs.google.com/document/d/1KMSJRNzS0xWbvrJMivqrG0FTd9UzuO4BgfgNnXoZS6k/edit?tab=t.0#heading=h.o2ja7vwh4zf)https://docs.google.com/document/d/1KMSJRNzS0xWbvrJMivqrG0FTd9UzuO4BgfgNnXoZS6k/edit?tab=t.0#heading=h.o2ja7vwh4zf
- Impactful maintenances 
	- Azure
		- DC Power maintenances on orca
		- FW Update on narwhal (PHX12 physical cluster)
		- FW Updates on GB200s 


**How do I reduce my own work by 50%?
- Automated (but human-in-the-loop) 
	- Comms 
		- Creating a sev per maintenance
		- Finding slack aliases for applied engines (rn I scrub Engine Manager manually) 
		- Finding RPMs per workstream
	- Maintenance 
		- Eri's Node Maintenance Controller 
- Visibility
	- Monitoring maintenances
		- go/next

	
    

-**
Azure, CW, CW-Contracted, GCP, AWS) 