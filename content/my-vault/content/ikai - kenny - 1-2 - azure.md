---
title: "ikai - kenny - 1-2 - azure"
---

### Scope
total # of clusters: 72
![[Pasted image 20260102082917.png]]
- we only need to do H100, H200, GB200s
- I'm working off this data [https://openai.chronosphere.io/dashboards/tmp-ikai-s-jan-2025-azure-repave-das?start=30m](https://openai.chronosphere.io/dashboards/tmp-ikai-s-jan-2025-azure-repave-das?start=30m)
- azure prefers to do entire clusters/colos at once, they need 4-8 hours
- I would like to set an upper bound of no more than 1800 nodes a day out for service at any given time (we have to do about 18.5k nodes total)
- we can probably do a bunch of small clusters
- I am asking for the ability to gradually roll the nodes in the big clusters; if so we would target doing 6% a day 

https://openai.chronosphere.io/dashboards/tmp-ikai-s-jan-2025-azure-repave-das?start=30m

applied side
- dont care about research
outage budget

anything you're running on a VM 
- u can send a packet that lets you break out into the outer host 
- can cause a lot of problems in azure
in shared fabrics - bigger risk 
dedicated hosts - if you have things you get into our own stuff 
- inside dedicated hosts 
they wanna do a FW update 
known about this vulnerability since november
nv told them they could update FW w o any downtime 
this is true for CX5

how much could we take out 

26% of raw nodes in fleet
its not a100e - if we use a conservative multiplier
throw the numbers off
can tolerate 3% of fleet being ok'

1800 nodes at any itme 
10% a day 
13-14 a day
a lot of api is most sensitive to australia and us 

for some clusters we're going ham
can we do it gradually 
either yes 
- 5-10 % of nodes everyday
	- >400 nodes
if they cant
- asked scott to extend the deadline
- theyre fully dedicated
at the first week - gathering risks about how long it takes

second week - can absorb 2nd week
can schedule one of these 
1300 

risk - rolling update

figure out what order we do these in 
1500 

start a sev channel
- chat will not be as impacted
- api 
- get 5 ppl on his side
	- split between research and 
- for bringing ppl back
- pain from 
	-  moving workloads
	- not easy to figure out 
- hwh - just need 1 1/2 people
	- when we try to bring up hopper - will lose 1 - 2 % 
- ikai - just need 5 people 
- cannot deprioritize

counting weekends
jan 18th 
microsoft will provide people on the weekend
if needed:
- move workloads 
- bring things back when theres problem
- get nvidia driver to 580 
	- test it on very small clusters - sweden central 
	- 158 a 
- planned maintenance states
1500 nodes
- 11Am - 8PM

- bring up capacity
priority 
- do all the small ones 
- research first 
- do applied last
if we can do rolling updates - we can get 70% additional date

num of big clusters 10

we would do 2 a day, and after 18th 1 a day

take out even distribution
work w simon 

- important US and EU 
- less important UK and australia and canada

published maintenance schedule for everything we do 
- open up a sev - bring in the managers and 
- janna, beckers table
if theyre doing lots of engine moves and deployments
- making sure thigns come up
start a thread in and infra strategy 


- eg I am working out a plan where we first do every host not running chat and API in a big batch, then we do chat while we migrate API to already upgraded hosts and slowly burn down the rest
- join it with engine manager
- research clusters first

- ([@anniez](https://openai.enterprise.slack.com/team/U09MBNFHZNC)) Planned scheduled maintenance dates for all the clusters on the following priority:
    - Small first
        - Research first then Applied
        - For Applied, take out even distribution of **EU**, **US**, Non-EU/US/UK
    - Big
        - Research first then Applied
        - Ask for ability to do rolling updates


how do we get all this implemented in the first half 