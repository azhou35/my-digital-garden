---
title: "nv patch huseyin batched notes"
---

01-18-2026
Scratch Pad
Huseyin Yildiz may know more about what updates got on the cluster - what had happened is:
yesterday morning we performed updates on one VMSS - nodes returned
we had an internal issue that required us to repave the cluster
today we see that all nodes are running on the LKG fw. 
 
we suspect that when we repaved last night, since huseyin's automation was set up the nodes automatically got the latest upgrade. however this only took 30 minutes compared to the typical ~4-6 hours, and also this was unplanned so there's a chance that if this needed IB FW updates, this cluster is sitting w misaligned CX7 x IB FW versions. 
Saloni Yadav Param Shah can you check w Huseyin on the above and help us understand if we still need to send this over to your team to finish updates, or if we can keep our nodes as is?
 
Huseyin chat:
Snapshot saw 592 nodes ready to be deallocated
All of them have been repaved, some are empty state 
530 having been updated 
Number of empty nodes 
From our pov the cluster looks good to go

By the time that huseyin snapped the empty nodes - we already had the deallocating additoinal capacity for internal issues 
Snapped a larger set of nodes which got repaved 

6pm azure returned cluste
11pm scale down
1-14 
 