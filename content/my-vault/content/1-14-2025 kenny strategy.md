---
title: "1-14-2025 kenny strategy"
---

kenny is taking it one level higher 
pen -> paper 
here where its gona b rlly shitty
this is waht the tooling looks like 
i dont wanna make guarantees where we ubild the tooling and we build the tooling and assume its done
still involved 
pawn it off to tools 

go from 5 engineers -> 2 engineer and a tool 

ask simon for the product vision about waht engineering support we need
we dont have a vision for these verticals 

every node in ndb is in the hardware lifecycle
scheduling
when do tools 
we're missing a souce of trtuh 
we want go/gpussot -? ndb 

usability 
enumerate all the workflows 

tpms step in when things get operationally toilsome

figure what maintenance means
3 ways 
- node level
- nvl level
- switch level
- cluster level
	- what dos cluster mean
	- ib fabric
	- kube cluster
how can we execute 
do we go node by node

what tooling we need
node ingestion system 
map that into our internal node chassis ids
is bot the right aproach or just an automated ysstem
how soon can we get to a solution thats scalable
build out api actions
autoation and tooling

14-18 months - we're part of the loops
go/next
for all these levels of hardware
define a hardware lfiecycle that ties 
hardware life cycle labels:
at every step of hwh life cycle there should be an action
- ready running job
- ready but validation
- 

it was a user
if i was running a job i want to think its a problem


once we define a hardware and cluster lifecycle
bake it into ndb and emit those metrics
zoku can pull it in 
for f33 it is currently i production
we'll take emitted data from ndb and post in zoku in zoku ui 
propagate down into brix level

talk to saagar, hwh team, talked to simon from a product pov 
think about the boxes
is ndb even the right thing to start

should be able click on can i pause vmss s
can i scal vms down to zero
can i scale up sclae down

we need to have our own tools to manage our own fleet
regardless


RMA specifically u make one rlly good CSp rlly successsfully and u take it succesful
CW what they wanna do 


good conversation w kenny
Fleet tpms are intended to see all the problems in the org and build things to put it together 

1. How do we build the tools that allow us to become an AI cloud? 
2. Maintenance - how do we define the boundaries and types and impact to other parts of the cluster lifecycle

Growth Plan
1. Kenny wants us to become indispensible TPMs that get called into DRI 
	1. How do we become the SMEs 
		1. e.g. Simon works on automations/agentic 
2. Weaknesses/strengths
	1. Proactively ask for feedback
	2. It's ok to be bad at coding

Actions:
- [ ] Talk to people
	- [ ] Saagar 
	- [ ] Simon 
		- [ ] on agentic 
- [ ] Define
	- [ ] Define the hardware lifecycle
		- [ ] I.e. every step of lifecycle there should be an action
	- [ ] Define the boundaries of tools (eg. Zoku, EM)
		- [ ] Define their workflows
		- [ ] Define their edge cases / limits
- [ ] UX Tests
	- [ ] Usability tests w customers on maintenance expectations
		- [ ] RPMs/Researchers 
		- [ ] Applied
	- [ ] Usability tests on tools
		- [ ] eg NDB 
- [ ] Design
	- [ ] Maintenance Tools 
		- [ ] UI for click-ops to trigger
			- [ ] For future automation / agency 
			- [ ] ie AI SRE but specifically for maintenance flow
		- [ ] Tools for CSPs
			- [ ] Take 1 as a lighthouse for others - e.g. CW bots
				- [ ] pilot go/next w CW? 
					- [ ] Ask Saagar about exposing go/next data w CW
	- [ ] Comms
		- [ ] Automations for Comms
			- [ ] Applied Notifier
				- [ ] auto tag on call
		- [ ] Intentional comms 
			- [ ] Cadence
			- [ ] CTA
	- [ ] Visibility
		- [ ] Dashboards for vis/tracking on update
			- [ ] Scheduling
			- [ ] Progress
			- [ ] Recovery
![[Pasted image 20260115222435.png]]
 ![[Pasted image 20260115222515.png]]