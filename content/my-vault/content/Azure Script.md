---
title: "Azure Script"
---


It's been tough for us all to manage the fires the last few days
We expected capacity to return, for us to scale up by late-afternoon. Our target execution time was 4 hours: in the worst case for 3 out of 5 clusters it extended over 12 hours, with non-trivial capacity pending until the next morning. While we improved capacity return marginally on 1/6, it was still not until 10PM that we could return clusters to production.


1. **1. Significant delays in update completion extended past nighttime hours.**
2. **1. We received pre-mature cluster readiness signals.**
	1. We need better signals. 
3. **1. Azure VMSS scale-up is unreliable.**



**

#### Asks:

Given that this work will extend across our entire Azure H100/H200/GB200 fleet, we have concerns that we will be able to reasonably accomplish maintenance given what’s broken in this process. 

- Operations need to get smoother. 
    

- We need end-to-end execution (from scale out to scale in) to finish before 7PM.


- We need reliable invariants.

- Any node we are able to scale in should have the new firmware. We should not be able to scale into nodes without the latest. This will enable us to build automations that keep humans out of the loop. 
    

- We need to bias for over-communication. 
    

- Especially in the early stages as teams are working through unknown issues, we’d like frequent updates to understand update progress. We want to coordinate in lock-step to avoid idle time from our engineers and set better expectations of capacity return. 
    

- We need to re-assess scope & feasibility. 
    

- For this maintenance to scale safely across our fleet, we need better reliability levels. To proceed, we need to reduce pace to what can be executed reliably with existing tooling and staffing, or increase dedicated recovery and maintenance resources
    



**

manually trying to recover
but thought things wer in a certain place
better tracking on our side and better info

tracking between us 
m

what would be helpfu for us 
if we reach a threshold
good enough to start to ramping up

work on a long tail
release the clusters

Sid - bring the VMSS team
single placement group - true - it was all or nothing 
dont put single placement group - false

was giving a specific number
some hens we cant scale into 
to make sure ur experience after handover

updates nic, host,backend switch 
sensitive to know 
moved traffic 

if you update the nic fw and the ib switch 
they have some dependency 
where certain versions 
switch update is very fast
long pole
