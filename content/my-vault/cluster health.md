---
title: "cluster health"
---

https://app.mode.com/openai_tf/spaces/fb3b3e896e4b

Research Cluster 
1. https://app.mode.com/openai_tf/reports/c98a5c692b59
2. https://app.mode.com/openai_tf/reports/c4bd08224a80 
3. https://app.mode.com/openai_tf/reports/89304cba95b4



Applied Cluster
1. GPU Infra on call
	1. https://applied-grafana-prod-c0g6hqfydgeae4fp.wus2.grafana.azure.com/d/adrkfuigtjf28a/gpu-infra-oncall?orgId=1&from=now-1h&to=now&timezone=browser&var-chrono_env=prod
2. https://applied-grafana-prod-c0g6hqfydgeae4fp.wus2.grafana.azure.com/d/adrkfuigtjf28a/gpu-infra-oncall 
3. https://openai-com.access.mcas.ms/aad_login

IB Dashboard
- https://applied-grafana-prod-c0g6hqfydgeae4fp.wus2.grafana.azure.com/d/feywsfvjg1s00f/ib-cluster-view?orgId=1&from=now-24h&to=now&timezone=utc&var-node_pattern=f6-gpu.%2A&var-cluster=f6&var-excluded_namespaces=image-preload%7Chwhealth%7Cscaling%7Cfluent-bit%7Cmonitoring%7Cwiz-sensor%7Ccilium%7Ccloudprober-host%7Cnode-agent%7Cotel%7Csecurity-observability%7Crdma-devices%7Ccloudprober-pod%7Cdaemons%7Ckube-system&var-included_namespaces=&var-DataSource=bes21l2cqopa8c 

IB Bench - ask Stephen 

cat.text 
get 50 nodes from the dashboard of iron 
iron-c


when nodes try to send over ib sometimes it times out 
this is how many nodes have that issue
this is per name space 
jrv had a lot of time outs 
theyre overwhelming this 
babsitting their job 

dashboard looks at what pods are on which nodes
we're trying to exclude on the infra one 
security-observability-vector

upload bandwidth dropping
found a researcher 
noisy negibhor - not codex 
the moent he stops his job everything went back to normal

after 

his stop his job 
go down the 

Usage

Shows the number of nodes currently in use by each job, grouped by priority.

Critical

[deniz](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=deniz)

- Titanium (island c superpod 3)

5720

[elias](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=elias)

- Titanium (island c superpod 3)

8

[kerengu](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=kerengu)

- Titanium (island c superpod 3)

8

High

[liny](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=liny)

- Titanium (island c superpod 3)

1792

[bwinter](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=bwinter)

- Titanium (island c superpod 3)

192

Mid

[mingchen](https://zoku.int.infra-sci.sci.openai.org/capacity?q=titanium+c&cpu=false&loc=titanium%3Ac%3A3&namespace=mingchen)