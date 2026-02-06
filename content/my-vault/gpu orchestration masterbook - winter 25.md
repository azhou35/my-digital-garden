---
title: "gpu orchestration masterbook - winter 25"
---

### Learning Plan
### **Phase 0** - [[GPUs Fundamentals]]
*Topics*
- GPU Components: SMs, HBM, interconnects
- Thermal vs power vs memory failures
- ECC errors (correctable vs uncorrectable)
- Why IB / NVLink issues masquerade as “GPU failures”
-> what does healthy GPU really mean?
-> which failures are noisy vs silent? 
-> what breaks first on GPUs? 

[[throughput machines, not latency]]
[[ib throughput issues]]

**Tasks**
- [ ] Review IB Dashboards from Mihai
	- [ ] [https://app.mode.com/openai_tf/spaces/fb3b3e896e4b](https://app.mode.com/openai_tf/spaces/fb3b3e896e4b) 
	- [ ] [https://applied-grafana-prod-c0g6hqfydgeae4fp.wus2.grafana.azure.com/d/df3cejkujypdsd/ib-stats-per-cluster?[…]ne=browser&var-cluster_short_name=c179](https://applied-grafana-prod-c0g6hqfydgeae4fp.wus2.grafana.azure.com/d/df3cejkujypdsd/ib-stats-per-cluster?orgId=1&from=now-6h&to=now&timezone=browser&var-cluster_short_name=c179)
	- [ ] https://grafana.sci.openai.org/d/feywsfvjg1s00f/ib-cluster-view?orgId=1&from=now-24h&to=now&timezone=utc&var-node_pattern=iron-gpu-d.%2A&var-cluster=iron&var-excluded_namespaces=image-preload%7Chwhealth%7Cscaling%7Cfluent-bit%7Cmonitoring%7Cwiz-sensor%7Ccilium%7Ccloudprober-host%7Cnode-agent%7Cotel%7Csecurity-observability%7Crdma-devices%7Ccloudprober-pod%7Cdaemons%7Ckube-system&var-included_namespaces=.%2A&var-DataSource=chronosphere
- [ ] Review node dashboards
	- [ ] TBD

### **Phase 1** Node / FW Layer
*Topics*
- Linux kernel & drivers overview for accelerators
- NVIDIA driver lifecycle (driver ↔ CUDA ↔ kernel compatibility)
- Firmware stack: BIOS, BMC, NIC firmware, IB switch firmware
- Node identity persistence (why a “new” node isn’t always new)
- Error amplification (one bad NIC → many job failures)

**Tasks**
- [ ] Review current FW stack of GPUs / failure points
- [ ] Snakey Diagrams? 

### **Phase 3** Cluster bring up: VMSS, control plane, K8s
*how does a cluster come into existence*
**Topics**
- Kubernetes: _“How the control plane works”_ (etcd, scheduler, controller manager)
- VMSS or equivalent cloud-scale node provisioning overview
- Control plane vs data plane
- Node lifecycle: provision → register → ready → schedulable
**Tasks**
- [ ] Create a bring-up timeline
[[kubernetes]]
[[container]]
### **Phase 4** Cluster bring up: VMSS, control plane, K8s
- GPU scheduling concepts: binpacking vs spreading
	- Gang scheduling
	- Topology awareness 
	- Large-scale ML schedulers: Google Borg, Meta
- Preemption, retries, job flakiness

### **Phase 5** Reliability
- Google SRE Book: 
	- SLIs/SLOs 
	- Toil/automation
	- Incident response
- Alerting vs detection vs diagnosis
- MTTR dominates perceived reliability
- How health metrics drift from reality

### **Phase 6** Data
**Tasks**
- [ ] Read Designing Data-Intensive Applications — Kleppmann
	- [ ] Chap 1-3, 5, 8
- [ ] Sign up for a snowflake tutorial
- [ ] Draft up a data model to define