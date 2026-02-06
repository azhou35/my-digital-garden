---
title: "overallocation team call"
---

- kick off how we can address this overallocation problem 
- we have discussed this at some level one-on-one
- talk thru the semantics of how 
![[Pasted image 20251030131048.png]]

RE: Rollout Plan. I see it as the following  

1. Correct clusters with Unallocated Capacity  >
2. Correct quotas with Unscheduled Capacity  >
3. Correct quotas with Idle Jobs >
4. The rest.

Open Questions we can chat about later in 1-1:  

- What's the design of how things will change? we'll allocate 15% flex per cluster and then 85% static?
- How do we keep what users will see on their side? 
- Assumptions
	- 

Failure modes:
- What will happen when GPUs someone is allocated on go unhealthy ?  



The tickets from the past week:
- https://openai.slack.com/archives/C07JGNSNQ1F/p1761757099099299 
- https://openai.slack.com/archives/C07MLKX96UR/p1761495123337789
- https://openai.slack.com/archives/C07MLKX96UR/p1761351681930499
- https://openai.slack.com/archives/C07MLKX96UR/p1761354042157519


**Notes
> “Goal today: align on the overallocation model and lock the rollout plan — buffer %, enforcement scope, timeline, and comms.” 
> Everyone is driving their own feature changes in zoku or brix - how do we operate as one brain 
- Outcomes
	- we want to ensure that when a researcher sees quota and they use it, they expect that they can use all their quota 
		- ie we never overpromise quota to them
	- also make it clear that since we're in a capacity crunch users r not losing gpus - its jsut that they were never rlly there 
- Failure modes 
	- what if a user tries to ask for more gpus 
- Definition
	- cluster-wide or quota wide and the nuances there 
	- ![Pasted image 20251030131048.png](app://20220ce037e49f900b315620c4dc22831f4b/Users/anniez/Documents/Obsidian%20Vault/Pasted%20image%2020251030131048.png?1761844248972)
	    - that means we can take flex capacity in mind when we implement this 


- Cluster-wide vs quota-wide    
- Rollout 
	- If we wanted to test it out on a cluster or two, what needs to be done before that? 
	- 
    

- UI Changes
    
- Path of least resistance**

one thing i want to navigate is pushback against the 15% buffer  from scheduling team/leadership/researchers - which i imagine is prob why this has dragged on for so long bc we're avoidant of haircuts 

there's a couple things i have in mind here -
- quantify how many gpus would actually be "cut" across the fleet (aka how many clusters are >85% and what %) - so the "haircut" feels less scary 
- re-litigate what acceptable "buffer" is - see if needs to be uniform or if it can be something that's lower for healthier clusters. or see if we can start with a smaller buffer 
- better qualify the problem statement here - scheduling team sees this as a hardware trying to reduce tickets vs researchers losing usable compute. better justify why leadership is vested in appropriate quota allocation 
