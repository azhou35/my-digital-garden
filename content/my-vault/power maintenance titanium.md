---
title: "power maintenance titanium"
---

research action: **Spin down** workloads if required prior to maintenance `brix pause` (or `brix dequeue --pause` is job is in the queue). Researchers can keep their pools running and they should resume after the maintenance.

scale down operations (30 min before start):
- put titanium -> clusterinmaintenance ([here](https://openai.slack.com/archives/C095SFQCD8T/p1755781589252959))
- scale down running workloads/ VMSSes  
	- ([here](https://openai.slack.com/archives/C08ER62LZ1B/p1741180214451709))
scale up operations: 
- set titanium -> deployed

post-maintenance researcher action:
- Anything manually started within the pool needs to be manually restarted.


Azure is performing a required power maintenance which cannot be delayed any longer and will impact GPU capacity in the `orca` cluster.
