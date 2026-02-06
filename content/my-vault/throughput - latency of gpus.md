---
title: "throughput - latency of gpus"
---

GPUs are optimized to:
- tolerate throughput 
- massive paralllelism 
- long, predictable kernels
- latency is hidden via oversubscription 


weaknesses: 
*cannot toelrate*
- low latency (branching/waiting/interrupts/cache misses)

 instead of waiting they will
 - launch thousands of threads -> schedule them in warps -> swap warps when one is waiting on memory 
	 - this only works if data is easily accessible (in HBM) and access pattern is predictable
	 - similar to an assembly line 
	 - SM / tensor cores are the workers, passing along inputs/activations/weights via data movement
![[Pasted image 20251225111529.png]]
