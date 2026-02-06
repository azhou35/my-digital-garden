---
title: "oai cpld and the switch fw"
---

- 4 hr downtime in the same window
- do the cpld update + fw in the same window
- they do need to do some testing on our side

[@ahelk](https://openai.enterprise.slack.com/team/U053NPBCWJC) - for future allocations, we plan to not allocate the cluster to 100%, we hope to allocate ~85% so quotas are less impacted by unhealthy nodes as there will be healthy nodes to flow in.  Next shuffle will be after break.just wanted to share - I understand the thread here is about how to ease the immediate pain the team is feeling.
currently there is an SLA for clusters to be >= 85 ~~90~~% healthy.  Iron (c) happens to be 6% unhealthy at the moment.because we allocate 100% of the cluster, the lowest priority quotas feel the 6% unhealthy nodes.if we allocate 85% of the cluster, no quota should feel the 6% unhealthy nodes,to your point, if the cluster exceeds ~~10%~~ unhealthy to >15%, we are in the same spot, but the cluster would be out of SLA and we'd engage hwh team to bring it back to SLA; whereas currently a 6% unhealthy cluster is within SLA.I'm not suggesting waiting until new shuffle -- I'm only sharing with you what we hope to do after break.  As I said previously, I understand there is a need to address the immediate pain (edited)

https://oai-research-ah.slack.com/archives/C09TY4RQBV1/p1763624754241889
for workload owners; the current situation is: we know this combination of driver/workload/cluster type basically results in false positives of this error. it legit crashes workloads and our automation detects and tries to remediateIt was worse than it should have been because nodes were not booting back into cluster due to another, unrelated failurethe bleeding will continue unless we repave the cluster (which is an option), or we move you elsewheregiven how much berry exists across the fleet, I feel like the right answer is just to repave this to 580 and be done. we will have to strategize.baremetal nodes take ~1h to boot so we will return to capacity recovery for the falsely implicated nodes tomorrow

yes this makes sense. so can u make a list with these columns:

total_node_count, % healthy (normalized off .85 SLA), target_healthy,

- team size
- CSP mix and diversity
- ability to execute maintenance operations

the promise I want my team to stand behind is: either you have (your quota) of GPUs 100% fulfilled, or we have opened a sev. we get paged at this threshhold, and we should be held accountable to it. it's hard to do that unless we align what we're promising (in terms of quota) with what we are aiming for operationally

![:+1:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/apple-small/1f44d@2x.png)1

[6:32](https://openai.slack.com/archives/C09PXLUK7QD/p1762558340692779?thread_ts=1762540062.151639&cid=C09PXLUK7QD)

15% is too big, ofc, and not a steady state, but short of giving up capacity turnup somewhere I don't currently have the bandwidth to make a dent in this number. (working on this problem)

![:+1:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/apple-small/1f44d@2x.png)1

[6:33](https://openai.slack.com/archives/C09PXLUK7QD/p1762558422374809?thread_ts=1762540062.151639&cid=C09PXLUK7QD)

there's a balance between "the number is too low and we let things slip" versus "the number is too high and we get paged all the time"practically, fleetwide, we're currently around 87-88% healthy