---
title: "kubernetes"
---

the control plane that runs containers (pods)
- decides which workload run on which machines and keeps them running
- decides placement, tracks desired vs actual state, restarts things
- metaphor:imagine a large resto where u tell the manager u want 100 identical meals being cooked at all times - u do not tell them which stove / which cook / which time - k8s is the manager
abstraction layers:
training job -> container (docker) -> pod (one or more containers) -> node (a machine) -> a cluster

- cluster - whole k8s control plane + all nodes
- node - machine/vm that runs kubelet and hosts pods
- pods - run the container (workloads)
	- a pod runs on one node 
	- can request gpu
- scheduler 
	- given constraints like taints / tolerations, resource requests
- k8s is declarative 
	- it constantly asks if desired state = actual state
- GPU nodes are put into GPU node pools so you can give them specific VM images, drivers, and scheduling (taints/tolerations) for engine/ML workloads. This avoids system pods crowding GPU hosts
- When we change the OS image, container host image, or firmware, we roll nodes in a node pool (often controlled by tooling like
cluster - node - pod relationship is what clusters team manages and monitors in production

- aks managed node pools
	- under the hood uses vmss
	- owns lifecycle/coordination to make pool operations easier
- node identity 
	- nodes get vendor/cloud metadaa and nodes are sometimes keyed by vendor/vendor specific id rather than stable names
- node pools / vmss / managed node pools (aks)

## why do we need k8s?
- without k8s human has to manually monitor when nodes die 
- with k8s you j say - i want job x running - k8s will find a node, start it, restart it if it crashes, move it if the node disappears

slurm was built for long-running scientific/gpu jobs, k8s is built for short-running job
but both: take job requests, look at avial resources, decide where to run the job, enforce fairness