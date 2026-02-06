---
title: "GPUs Fundamentals"
---

**What are the errors you can see**
### Storage Primer
Issues come in four ways:
1. Persistent storage
	1. object storage (S3 / Blob) / network file systems (NFS / Lustre / GPFS ) / bloc storage (PD, EBS, local SSD) / node-local NVMe
2. Data ingestion
	1. Check point downloads / datasets shards / containers images / model weights 
3. Runtime i / o
	1. mmap / read() / page cache / PCIe DMA / GPU memory copies
4. GPU execution
	1. HBM / SRAM / Compute 
		1. SRAM is the tiny whiteboard next to the compute - used for L1/L2 Caches
			1. no refresh 
			2. however it has huge area cost on the chip 
		2. HBM
			1. isued for model weights , kv cache, insane bandwidth 
			2. its a big storage next to gpu 
		3. many GPU utilization problems are actually memory hierarchy problems
GPUs are uniquely sensitive to storage - CPUs tolerate slowness bc "CPU threads block / OS scheduler hides latency - you get slow, but it still works".
GPUs expect steady streams of data (bc they are [[throughput - latency of gpus | throughput machines, not latency ]]) - **starvation** -> idle SMs -> timeouts/watchdogs/retries. 

**GPU data path**
1. dataset lives in object storage (S3/blob)
	1. failure modes: throttling
2. node downloads shards -> local disk / cache, node local NVMe 
	1. NCCL collective hangs
3. CPU preprocesses
4. data copied via PCIe into GPU HBM
	1. packet-based (like a network) w high frequency, sensitive to temp/power 
5. GPU executes kernel 
![[Pasted image 20251225134856.png]]
![[Pasted image 20251225134909.png]]

### Thermal/Power failures
- hotspots in HBM stacks, poor airflow, thermal throttling 
- symptoms
	- itermittent crashes unde sustained load 
*Power
- transient voltage drops 