---
title: "LON60PrdGPC01"
---

**Impacted Cluster: c28 (AustraliaEast)**  

- **What:** Azure needs to reboot 100+ IB switches on old firmware versions in AustraliaEast

**Expected Impact:** The cluster will have no infiniband for 9 hours during **off-peak**  

- Start: Wed, 07/23 @ 3PM PST
- End: Thu, 07/24 @ 1AM PST

**![:weewoo:](https://emoji.slack-edge.com/T03025Z7DT4/weewoo/20619c708ba79c5d.gif)** **Required Action from Tenants**  

- Confirm that your engines can run without stable IB.
- Confirm that you can take the capacity impact for 4 hours at off-peak.
- **IF you need** **_temporary_** **backfill capacity**
    - **Let us know # of GPUs (if not 1 for 1) and in target regions.**

Tenants:  

- [chatgpt-c28](https://engine-manager-web.engine-manager-0.internal.api.openai.org/reservations/applied:c28:openai:topologyreservations:chatgpt-c28/view): 616 A100-80GB
    - Notable Engines: [gpt4o-1p-r1-0428](https://engine-manager-web.engine-manager-0.internal.api.openai.org/engines/gpt4o-1p-r1-0428/view)
- [api-c28](https://engine-manager-web.engine-manager-0.internal.api.openai.org/reservations/applied:c28:openai:topologyreservations:api-c28/view): 552 A100-80GB
    - Notable Engines: [o3m-api-ft-nbv4](https://engine-manager-web.engine-manager-0.internal.api.openai.org/engines/o3m-api-ft-nbv4/view), [gpt4o-api-2408-3-v](https://engine-manager-web.engine-manager-0.internal.api.openai.org/engines/gpt4o-api-2408-3-v/view)
- [safety-c28](https://engine-manager-web.engine-manager-0.internal.api.openai.org/reservations/applied:c28:openai:topologyreservations:safety-c28/view): 320 A100-80GB
- [imagegen-moderation-c28](https://engine-manager-web.engine-manager-0.internal.api.openai.org/reservations/applied:c28:openai:topologyreservations:imagegen-moderation-c28/view): 256 A100-80GB
- [inference-eng-c28](https://engine-manager-web.engine-manager-0.internal.api.openai.org/reservations/applied:c28:openai:topologyreservations:inference-eng-c28/view): 192 A100-80GB
    - Lots of canary engines and test engines