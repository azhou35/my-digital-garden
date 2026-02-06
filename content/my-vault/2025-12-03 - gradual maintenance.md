---
title: "2025-12-03 - gradual maintenance"
---


gcp clusters
- c230
- c294
- c298
- c263
	- 8736 GPUs 
	- 5 groups of 224
- c253
	- 14960 GPUs
	- **4 blocks of 224 VMs**
	- **1 block of 216 VMs**
	- **2 blocks of 214 VMs**
	- **1 block of 212 VMs**
	- **10 blocks of 10 VMs**
	- **2 blocks of 8 VMs**
	- **1 block of 12 VMs**

**What is realistic in Jan for c263**
P0 
- If we dont evac? 
- Spread out the drain 
- Repave c263 into smaller clusters?
	- This is not set up for GCP - any plans 
	- https://www.notion.so/openai/Applied-engine-cluster-ZBS-repave-plan-27e8e50b62b080859c93cae386ea25a6?source=copy_link

"ILB" stands for Inference Load Balancer. It is a critical component for distributing inference traffic efficiently across engines and modalities (such as embeddings, DALL-E, TTS, Whisper, Sora, etc.) in OpenAI’s infrastructure.⁠[](https://www.notion.so/InferenceLB-V2-1228e50b62b08084b9befb8087df76b4?pvs=53#1298e50b62b080688994d04db7fbba02)⁠​

Start the meeting to level-set on where this is coming from
- This is in relation to running maintenances on our applied clusters
- Usually the practice is to just quarantine and run the maintenance 
- But now w our new GCP clusters 
	- The clusters are larger 
	- The maintenance requirement is more frequent (1x a quarter)
- And we saw this with our last maintenance on c253, where a 4 hr maintenance ended up spanning across a weekend and affecting important products like sora 
- We are able to punt out our next maintenance for c263 to next quarter, and i wanna discuss at a high level what we should do to mitigate the disruption / operational load across clusters / fleet / scheduling

Alex/Xintian Yang -  scheduling

https://docs.google.com/document/d/1KMSJRNzS0xWbvrJMivqrG0FTd9UzuO4BgfgNnXoZS6k/edit?usp=sharing

Maintenance itself wasnt the problem 
Scheduling POV uses infiniband partition 
should we separate this cluster into 4 infiniband partitions 
and hen we tie that to the blocks
can build the tooling to evacuate 1 parittion at an end

turn off this domian only evacuating 25% of this cluster
c177
purposely split it up

is partial maintenance something we should prioritize 
what makes you want to evac
instead of assming redunacnesi

we are no longer concerned about size of cluster bc assume tensor api 
minimizing disruption based on customers

maintenance domain is ib 
meta data from the provider 
hard to aggregate them and hard to partition

decently large maintenance domains 

tagging things as under maintenance
have concept of all our domains and work with our providers to understand what our domains our
make sure that our ndb has all the info necessary

if gcp can give us mapping of blocks/subblocks to nodes
we can do that mapping back to our group
single node in ndb
- has subblock 
- block 
- decide at which level we want to drain 

confirm if our ib domains can align to these domains 

you want to see which ib domains are from a block 



https://app.sigmacomputing.com/open-ai-azure/workbook/OpenAI-GPU-Single-Source-of-Truth-go-gpu-ssot-1zRqIrPg0YtB7FS7RNKRg5?:savedView=321b431f-90a0-4188-b2c6-8ca4af414f78&:nodeId=KtJjLbmB5g


PDX2 
- CPLD 
	- known bug - for 10% of nodes if a failover is triggered it would fail 
- switch upgrades
- retries a lot 
script theres multiple retries required
1) cpld has to be sequential to ib switch 

8 hrs 

low confidence in cpld
not an urgent upgrade to do 
can be done on a rolling bais

decouple the cpld and ib switch 
do it in a rolling manner

1) 8hr maintenance 
2) take cpld later
	1) 3 retries per switch 

Monday - a couple of Switches
Wed - 
if not using ib fabric

PDX2

