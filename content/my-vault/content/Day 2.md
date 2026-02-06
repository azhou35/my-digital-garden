---
title: "Day 2"
---

c199
no impact


c186

go run personal/pzhao/scripts/cluster_impact.go --clusters c220 c216 c197 c165 c143 -ip 15 -e tsv

go run pzhao/cluster_impact.go --clusters c199 c200 c186 c211 c123 c166 c155 -ip 15 -e tsv

personal/pzhao/scripts/cluster_impact.go --clusters c256


### Scripts
```
for c in c199 c200 c186 c211 c123 c166 c155; do
  go run personal/pzhao/scripts/cluster_impact.go \
    --clusters "$c" \
    > "/Users/anniez/Documents/maintenanceimpact/cluster_impact_${c}.txt"
done
```

To get Pete's script

```
for c in c199 c200 c186 c211 c123 c166 c155; do
  go run personal/pzhao/scripts/cluster_impact.go \
    --clusters "$c" \
    > "/Users/anniez/Documents/maintenanceimpact/cluster_impact_${c}.txt"
done
```
go run personal/pzhao/scripts/cluster_impact.go

Top products by GPU share (1962):

- ChatGPT: 824 GPUs (42.0%) @chatgpt-infra-oncall
- Other (codex, safety, etc): 572 GPUs (29.2%) @codex-oncall @safety-eng-oncall
- Images: 190 GPUs (9.7%) @image-gen-service-oncall
- Sonic: 176 GPUs (9.0%) @search-oncall

_Product: ChatGPT_  - @chatgpt-infra-oncall
 Total: 824 GPUs (42.0%) | reserved (weighted by GPUs): 32.4% (~267.3 GPUs) | replicas: sum=49.0%, wtd avg=5.1%  
 `gpt5-api-250807-q`  
 • GPUs: 160 (8.2%) | reserved: 0.0% | replicas: 3.0%  
 `gpt41s-2504-3-v`  
 • GPUs: 160 (8.2%) | reserved: 56.7% | replicas: 2.0%  
 `gpt4o-api-2408-3-v`  
 • GPUs: 152 (7.7%) | reserved: 76.2% | replicas: 5.0%  
 `gpt51-apip-251113`  
 • GPUs: 80 (4.1%) | reserved: 0.0% | replicas: 1.0%  
 `gpt5-cswic-250807`  
 • GPUs: 80 (4.1%) | reserved: 0.0% | replicas: 14.0%  
 `gpt4o-api-2405-3-v`  
 • GPUs: 76 (3.9%) | reserved: 80.0% | replicas: 16.0%  
 `gpt5-1p-sw-p-0807`  
 • GPUs: 60 (3.1%) | reserved: 0.0% | replicas: 3.0%  
 `gpt5-cocoon-ev3`  
 • GPUs: 36 (1.8%) | reserved: 0.0% | replicas: 1.0%  
 `gpt5-1p-sw-i-0807`  
 • GPUs: 10 (0.5%) | reserved: 0.0% | replicas: 1.0%  
 `gpt5-1p-sw-c-0807`  
 • GPUs: 10 (0.5%) | reserved: 0.0% | replicas: 3.0%

Prompts
```
You will be given a tab-separated list of engines with 3 numeric columns:
(1) GPU count, (2) % reserved, (3) % of replicas in cluster.

Task:
1) Compute TOTAL GPUs across all rows.
2) For each row, compute "% of total GPUs" = GPUs / total * 100.
3) Group rows into PRODUCTS using these prefix rules:
   - ChatGPT: engines starting with "gpt"
   - Codex: engines starting with "codex" OR "sb-nv4-codex"
   - Images: engines starting with "ig" OR "img"
   - S2S: engines starting with "s2s"
   - Sonic: engines starting with "sonic" OR "snc" OR "flx-sonic"
   - M4: engines starting with "m4" OR "eg-m4"
   - Safety: engines starting with "safety"
   - Other: everything else
4) For each PRODUCT, output a header line:
   *Product: <name>*
   Total: <sum GPUs> GPUs (<% of total GPUs>) | reserved (weighted by GPUs): <wtd % reserved> (~<reserved GPUs>) | replicas: sum=<sum replicas %>%, wtd avg=<wtd avg replicas %>%
5) Under each PRODUCT, list each engine in this exact Slack-friendly format:
   `<engine-name>`
   • GPUs: <count> (<% of total GPUs>) | reserved: <reserved %> | replicas: <replicas %>
6) At the very top, add a *High-level product impact summary*:
   - Rank products by GPU share (top 4 + combined %)
   - Call out where reserved capacity is concentrated (top products by reserved GPUs + key drivers)
   - Call out replica concentration using weighted avg replicas (and note that replica sums can exceed 100% if variants exist)
7) Formatting requirements:
   - Engine names must be in inline code using backticks.
   - Keep it copy/pasteable into Slack (no tables).
   - Use 1 decimal place for percentages and reserved GPU counts.

Now process this input:
<paste the engine rows here>

```

fleetwide-azure-reimage

we are going to do our best to be non disruptive, however, there is a chance this will impact users. The most likely culprit is that we are going to remove up to 3% of GPU capacity from the inference fleet every day during non peak hours. There is a chance user workloads are impacted without a failover. This is why we have looped in API infra and chat infra oncalls. We will do our best to spread regions and clusters so that we don't take out 100% of serving capacity, but this is a very manual and imperfect operation.Removing some serving capacity comes with the risk of increased latency or error rates where ILB is not able to route away - and in the case of ev2 engines, higher error rates.Unfortunately, due to the timing imposed on us by Azure's security team, there is not much we can do right now to derisk this further. In some select cases, we may move engines, but we are not going to be able to move all workloads AND complete this maintenance in time. We are going to need every oncall to be aware of the maintenance schedule, have knowledge of if their workloads will be impacted, and be ready to migrate if needed.


09:00 - Azure starts maintenance
10:00 - Azure updates x y z 

