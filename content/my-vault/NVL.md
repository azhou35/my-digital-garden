---
title: "NVL"
---

the problen NV had to solve:
- PCIE is too slow for GPU <> GPU traffic at scale 
	- multi-GPU workloads need high bandwidth low latency 
solution:
- build dedicated GPU-only interconnect
- point2point, packetized, cache-coherent link 
- allows
	- GPU A to read/write memory on GPU B without going thru CPU memory

NVSwitch 
- crossbar switch for NVL traffic
- GPU <> GPU at full NVL bandwidth 

![[Pasted image 20251226153904.png]]