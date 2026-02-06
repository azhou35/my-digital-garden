---
title: "1-15-2026 hwh weekly"
---



Saagar’s back from maintenance!
general vibes
- cerebras announcement
- we’re not managing the hardware ourselves

new hardware [here](https://docs.google.com/document/d/1yqQ7AlY-RY7wBDO0leeTJFQKsIg92hOrfWn3wd6YYmU/edit?tab=t.0#heading=h.ngd9jylk6xwq)
nv research
 95 clusters complete, 33 clusters to go
    - **Averages this week:**
        - ~12 clusters/day
    - 16 clusters left

### gb300s
- f30/f33 show regressions for IB XDR issues
- 3 way escalation nv<>azure<>oai

### titanium
- berry low azure host memory - no explanation why 

### amd 
- chromium is not usable 
### Buckets of operational issues
1) Workloads are not working
2) capacity
3) As we increase CW clusters also increase loads of the CW bot

### Frontiers handover
Renaud is setting up a third issue

![[Screenshot 2026-01-15 at 4.31.09 PM.png]]

generalizing NVSwitch (not NVLink + switch)
rack-level and cluster-level validation

things we care about the health of:
- nvl
- ib
- how do we automate
	- cluster turnup

maintenance automation
- how to make it automatable or clicks op a ble

**vendor integrations eri dyli godwin frankliu**
buckets
- inventory
- telemetry/health signals
- api integrations for vmss nanny / baremetal 
- create a coherent interface for what we need w vendors 
what is our desired future here


###### thought:
1. evangelize maintenance
2. make a doc 
3. make a channel

### applied on call 
*demo by stephen*
very manual
- eg nvl validatoin
- piggy backing on ib bench pods
![[Screenshot 2026-01-15 at 4.54.18 PM.png]]
```
applied_hwh_validation.py c372 preflight
```

![[Screenshot 2026-01-15 at 4.55.50 PM.png]]![[Screenshot 2026-01-15 at 4.59.15 PM.png]]


