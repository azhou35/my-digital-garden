---
title: "2026-02-09 calcium rolling maintenances"
---

Risks:
https://brix-api.pom.frsh2.sci.openai.org/brixxy/capacity/calcium_b/syn-codexshine/b200?q=codexshine&includeCpu=%220%22&includeGpu=%221%22

Carpus Derisking Plan:  
If we can get as many healhty gpus going into the maintainence, I think we should have enough buffer to not feel 500 nodes switching in and out.

Calcium A
I'm move interactiveagents2 from calcium a to f5 and keeping it as flex.  That should add another 928 to the buffer.  so I think calcium (a) should be okay

Calcium B 
H3 is running here,  foundations practically have the full cluster I think we can increase their priority during maintaince, so that PT lose gpus first giving (528 buffer) on top of the buffer from the cluser being in SLA,   PT might be giving up B200, but I heard its only used for grading which should be tolerate gpus fluctuation.   It might be going to VITA and they are on the fence about taking it, I imagine they can only use it for grading as well

Requirements:
~8.3k GPUs
Priority: alr critical


### Eri
1. Share feature trackers w OCI, AWS, GCP 

## Fleet H1 All hands 2026
- how to simplify and meet the users where they are (CAAP)
- who do we need to partner the most with? 
	- more directly with applied teams 

ikai
- there are 5 ways of doing everything ![[Screenshot 2026-01-28 at 3.29.02 PM.png]]
- api for fine tuning team
- ppl are asking to use openai stack to train their own models
	- enterprise customers who want to deploy our own applied products
	- we need to meet their compliance bar
	- 200M
	- working w manufacturers to train these things
- we're spending 1B on FIber links
- get more compute providers for research 
- we're getting cerebras in azure 
- DCs that run 30K GPUs
	- 490 companies in fortune 5000
	- a bunch of those
![[Screenshot 2026-01-28 at 3.35.51 PM.png]]
scheduling
- maintenance work exposes the rough edges 
platform
![[Screenshot 2026-01-28 at 3.46.31 PM.png]]scv - 
![[Screenshot 2026-01-28 at 3.59.00 PM.png]]