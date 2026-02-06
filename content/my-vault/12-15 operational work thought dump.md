---
title: "12-15 operational work thought dump"
---

1. making it so when we get a cluster, everything we need already works. Carolina does a good job but there's always _something_ that we have to go back and forth to feature-flag properly
2. getting actual momentum behind open questions. nvme/storage is a big one lately between [#proj-ssd-kv-cache](https://openai.enterprise.slack.com/archives/C098PGWCQMT) and some old asks I had. I believe frontiers folks would love stronger attention on kernel/hypervisor issues too
3. clear escalation path with redundancies for critical infra. right now all of these are single point of failure, from my perspective
    1. infiniband
    2. node automation
    3. telemetry
4. reducing the amount of variance between various azure clusters. I want all my clusters to work similarly, the training/inference split is something we should try to shift away from. IIUC azure is also poised for it