---
title: "aws sync pre-dev"
---


hardware
backwar
automation gaps

amount of api maintenance


every rma turns to jira adn its our health signal
they have an inventory of 

sample 
close their 

depends on error and research or applied 
- ask Eri if its applied 
- Mihai if its research
- not sure if theres good binding from node -> switch 
inventory of every node that they we re
we request repair for 

before we got a cutsheet
built an api based thing for denton 

getting both inventory thru coreweave

inventory where we get stable identifiers 
- we want to be able to say we were on this node 
- we got it back and node 
- memory 
- so we dont trust it 
- a core requirement. 
davis / anuj 
- reach out how to understand into the early convos
- here is what we want in the inventory 
- binding into the stable 

azure has 

oci - has two variants
bm 
oci cloud 

aws


google calendar 
- maintenance calendar 
- we weren't really using incidents
file a pre-emptive incident -> ways to notify ppl in cluster 
coordinate everything in the incident 

totally open to collecting them
albatross - things coreweave 
phoenix 

gpu/ssot 

tito is trying to build something 
have the independent sources 

maintenance cluster 
rpms 

in applied if we quarantine - we can 

research we bind quota to console 

starting to build a repository to put them into our systems
living doc 
telemetry 

cw-azure we get it from azure 
cw-direct clusters - getting telemetry 
gcp 



Only thing thats working is VMSS Nanny 
Reimage is a hack 


RMA - 

Prioritize the instance ID 
- Publish the vendor specific
- Pipe it thru Kube node
- Can automation can get instance id and what azure region and what is region 
- Blocker:
	- Vendor chassis id - ndb is more field 

inventory may not need it for vm - based things 
- we dont need to boot server things 
- all vendors we want chassis id 

oci - we need chassis
- we want stable cluster name 

rma: 
- sujith automation 


- I think for an individual researcher, the problem is that they have been told they have 1024 healthy GPU to run their job, those GPUs don't actually exist, their job cannot run, fleet is aware that a known % of GPUs are not healthy so there's not much actionable we can do and it's frustration all around. Exacerbated by researchers often planning and staggering their jobs so when the first job doesn't run, the plan doesn't work out. One big contributing root cause of this is overallocation. We want to make sure that any GPU a researcher thinks they have is actually available and schedule-able.
- This would require RPMs to essentially "de-allocate" some capacity to stop overallocation. This may feel bad to teams at the onset, but actually their daily experience scheduling will feel better and they'll be able to plan around actual capacity they have and avoid really frustrating experiences
- Further, I think all of this is even worse because a lot of individual researchers don't know about overallocation. In a previous life when I was doing allocation, if there was overallocation it was widely announced the overallocation percentage so people understood that their jobs would need to queue before being scheduled. Now I feel we have an expectation that our jobs will schedule instantly while overallocation is also on and I think this misalignment in expectation just creates bad vibes.
- For flex, one other thing that I know we all know about is fairness. One issue here is that people seem to squat compute endlessly. For example,  this week in alignment we found someone squatting from before the whitelists were rolled out. So I think we need to add a point about fairness in flex (and no squatting on other people's compute) in order for flex to be operational or a few people can soak up all the flex for everyone

![:plus-pulse:](https://emoji.slack-edge.com/T03025Z7DT4/plus-pulse/cd9d88c3d34188b6.gif)3

![](https://ca.slack-edge.com/E03025Z7DT4-U05BAEV0K7G-aa28cfb0c739-48)

Jos Kraaijeveld![:jos-kraaijeveld-helping-you-move-your-engine:](https://slack-imgs.com/?c=1&o1=gu&url=https%3A%2F%2Femoji.slack-edge.com%2FT03025Z7DT4%2Fjos-kraaijeveld-helping-you-move-your-engine%2Fecef9c1fe5abb957.gif)  [Today at 10:39 AM](https://openai.slack.com/archives/C09PXLUK7QD/p1762540795311789?thread_ts=1762540062.151639&cid=C09PXLUK7QD)  

100% yeah the short-term world I want to try and promise to people is "in quota your job will run as soon as you schedule it" and "on flex your job will run at some point (in reasonable time)"
