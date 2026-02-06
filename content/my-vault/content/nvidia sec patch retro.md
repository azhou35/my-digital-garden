---
title: "nvidia sec patch retro"
---

### Kenny
- peter talks thru scheduling problems 
	- pending pods
- every engineeer says this is wwhat we faced
	- this is what we fixed along the way
- this is what is long tail
- -> is there anything we need to prioritize today 
- how often does this happen
	- data on this 
	- we need to work on this tooling
	- bc the next month alone we have at least 5 full cluster maintenances, with varying scopes and skus
		- this many maintenance ops
Goals:
- create the urgency 
- here's whwat we accomplished
- heres the problems we ran into this
- to wrap everything up this is the long tail problem
- Agree internally on what the biggest problems where
	- work w Evan Jane Jack

Speaking points:
- “Along the way, we did make progress:
	- We unblocked X class of pending pods
- “What remains — and what worries me — is the long tail.
	- Even after maintenance ended, we saw clusters stuck in partial recovery because of [pending pods / scheduler blind spots / unclear ownership].
- “The reason I want to drive urgency is simple:
	- next month we have N maintenances across M clusters.
		- If we don’t change anything, we still expect toil for our on cals”

this is all emergent behavior coming from maintenance
start at 0 validations
they udpated the firmawre on the nics

a general theme ive been hearing is 
- better more detailed signals for maintenance w all these systems
- its a huge known temporary hardware health event 
	- quota specs from scheduling
	- signals w azure/csp on maintennace
	- signals on cluster healthiness
		- readiness to return
- we need some sort of control plane or maintenance
	- rn for small scale its a health even
	- large scale we just treat it as an operation
- signals w customer expectation
	- e.g. scheduling / engines 



surfaces / levers / knobs 


### Vendor Sync
![[Screenshot 2026-01-23 at 12.32.31 PM.png]]
we have two implementations between research / applied
- cw is asking us to add more ticket standardization whic requires us to add one check to anotehr
![[Screenshot 2026-01-23 at 12.33.15 PM.png]]
- topology data (fabric/network/racks)
- life cycle (two way interaction w vendors)
- ticketing workflows (two interaction)
	- today we do slack -> linear -> gpt 4.5
	- usually us to vendor, sometimes cw to us
- build a coherent abstraction fleet-wide that works for all of our vendors 
	- all while keeping the lights on 
- Converge on apollo becoming this layer
- everyone building their own abstraction makes sense
- standard set of tools to communicate with vendors
- getting the apollo team sooner rather than later
how to make this abstraction 
- reimages?  
vendor integration
- majority in applied
- oci in research 
- what is our goal?
	- single layer cross-research/applied/caas
- concern around stack convergence 
AI: 
- Apollo runs on 
	- does apollo work with what we have today for researcher or does it replace it?
	- BMC access -> fleet
![[Screenshot 2026-01-23 at 12.45.55 PM.png]]