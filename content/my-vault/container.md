---
title: "container"
---

tiny, self-contained package that bundles _your program + everything it needs to run (libraries, runtime)_ and gives that package a lightweight sandbox on a machine.
e.g. it's **shipping container for software**: everything your app needs goes inside one box so that the app behaves the same whether it’s on your laptop, CI, or a 1,000-node GPU cluster.

this results in easy reproducibility - aka two ppl both pulling an app get the same code, same Python version, same libraries
enables autoscaling, rapid canaries, easy rollbacks, and automated restarts if something

- They **share the host kernel**: containers are not full VMs; kernel bugs or misconfiguration at host level still affect all containers.
- For **GPUs / IB / special hardware** you often still need drivers or privileged setup on the host (device plugins, runtimes). Containers alone don’t eliminate that operational work.
- Containers add an orchestration layer (k8s) and operational complexity — but that complexity buys huge operational leverage at scale.
