---
title: "researchers pov"
---

, just circling back that our jobs are running!Yes ofc, here's how GPUs translates to jobs on research side (caveat: my understanding of how quota works is patchy so don't know how quota fits in the picture here):We use the GPUs in 2 main ways:  

- training jobs (peashooter clusters)
    - if nodes go bad this completely stops/halts model training
- engines for grading/evals/general analysis calls
    - if these nodes go bad this slows down but not completely stops our jobs, because these are all load balanced behind bus

Losing nodes to unhealthy state on training jobs side is by far worse than on losing on the (grader) engines side. It's fixed how many GPUs are needed for a 1 training run (i.e. 352 H200s needed for the train cluster for thinky model posttraining, we need a continuous block in an island for this, if we dip under that number due to unhealthy nodes then we simply can't complete the cluster for a training run, can't split across islands)Re team allocation, it's just an informal process to coordinate on the team, which teammates will use team-budget GPUs by spinning up engines/peashooter clusters on the available nodes. And we just discuss which folks need them for higher pri reasons. In general, everyone is responsible for their own jobs' nodes health - there isn't a dedicated person on the team who manages the health of the cluster. Jobs often break (sadly) and we go to [#oak-alpha](https://openai.enterprise.slack.com/archives/C09DCA01WFP) and [#strawberry-support](https://openai.enterprise.slack.com/archives/C05D37ZDCEQ) and then also [#compute-support](https://openai.enterprise.slack.com/archives/C07MLKX96UR) (here) if the job breaks and we don't know what happened and it seems like infra is the underlying cause

[5:16](https://openai.slack.com/archives/C07MLKX96UR/p1761340619357909?thread_ts=1761251447.277219&cid=C07MLKX96UR)

Hope that's helpful [@kenny](https://openai.enterprise.slack.com/team/U066U1AK7NC), but let me know if that doesn't answer the exact question cc: [@jrobinson](https://openai.enterprise.slack.com/team/U084D8FTDU0) in case you have add'l thoughts you'd like to add

![](https://ca.slack-edge.com/E03025Z7DT4-U066U1AK7NC-7679a31c365c-48)

Kenny Nguyen  [Yesterday at 5:36 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761341760663289?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

This is extremely clear and useful

![](https://ca.slack-edge.com/E03025Z7DT4-U07BQ7FDKC2-ecd9e461d4d9-48)

Saagar Patel  [Yesterday at 5:37 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761341842642379?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

related question: within a single quota, do we have a way to prioritize training jobs over the engines? that is, if _something_ is going to get descheduled, a hint to suggest importance of the job to perhonen? (maybe [@leochen](https://openai.enterprise.slack.com/team/U06FYM1Q423) can speak well to this) (edited) 

![:plus1:](https://emoji.slack-edge.com/T03025Z7DT4/plus1/dcb953218701d881.png)1

![](https://ca.slack-edge.com/E03025Z7DT4-U06FYM1Q423-bdd496060c7f-48)

Leo Chen  [Yesterday at 5:38 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761341912833189?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

> do we have a way to prioritize training jobs over the engines?

Today is done by priority, i.e. critical > high > mid > low. (edited) 

![](https://ca.slack-edge.com/E03025Z7DT4-U066U1AK7NC-7679a31c365c-48)

Kenny Nguyen  [Yesterday at 5:41 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761342062975779?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

Is it good practice to essentially schedule:  

- training jobs (peashooter clusters)
    - as Crit
- engines for grading/evals/general analysis calls
    - as High

![](https://ca.slack-edge.com/E03025Z7DT4-U06FYM1Q423-bdd496060c7f-48)

Leo Chen  [Yesterday at 5:44 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761342259366389?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

yes, with existing priority system, this could achieve what we want here. Meanwhile, we are working on a new workload api which will allow users to use critical priority for different pools and specify relative priority among them.

![:nice5:](https://emoji.slack-edge.com/T03025Z7DT4/nice5/d11e3563ad627338.gif)1

![](https://ca.slack-edge.com/E03025Z7DT4-U08APMJU62F-4d9c8b8a4a00-48)

Austin Chan  [Yesterday at 5:47 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761342423716579?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

We've been following the practice of putting everything as `critical`, including our grader engines. We have done this just to make sure our grader engines don't get preempted by someone else spinning something `critical` in the cluster (maybe inadvertently). But `high` protocol for graders makes sense and would help us here, but this allows other people to kick out some of our grader compute I guess. A relative priority within `critical` would be awesome!

![](https://ca.slack-edge.com/E03025Z7DT4-U06FYM1Q423-bdd496060c7f-48)

Leo Chen  [Yesterday at 5:48 PM](https://openai.slack.com/archives/C07MLKX96UR/p1761342487009929?thread_ts=1761251447.277219&cid=C07MLKX96UR)  

feel free to follow progress here [#prj-peashooter-on-brix-workloads](https://openai.enterprise.slack.com/archives/C09HKQJBVBJ)

# Engine Cluster Creation: The State Machine

# What/Why

In the past quarter or two, we’ve removed many of the manual steps from engine cluster creation (for example, ~6 PRs → 1 PR): toil has been significantly reduced, and the happy path of cluster creation can take under half a day or so right now.

However, right now, engine cluster creation is still largely engineer-driven: that is, we rely on humans to drive/retry a series of steps (go/newcluster) and perform validation until the cluster is in production. We should move towards an automation driven state machine, removing humans from the loop as much as possible.

# The Plan

Here’s what the new flow is going to look like:

1. [**Planned**] A new cluster is added to NCDB, via either the spreadsheet (go/gpu-supply) or go/em.
2. [**Planned → Provisioning]** Our controller watches the subscription the cluster exists in. Once enough CPU quota is added by Azure for us to create a cluster, the controller marks the cluster as “Provisioning”.
3. [**Provisioning → Provisioned**] We run a [buildkite job](https://buildkite.com/openai-mono/cluster-bootstrapper) that is responsible for performing the set of terraform applies and applied spec that we need to provision a new cluster
    1. Why buildkite? Our controller doesn’t have access to github actions. And buildkite works well with the deploy systems, so it’s a reasonable choice for a stopgap. In the future, we should probably consolidate towards just the controller, or maybe temporal/similar.
4. [**Provisioning → Provisioned**] Our controller creates the VMSSes for the cluster (via ASO).
    1. Note that this state transition is the same as the previous one, that’ll probably change.
    2. It may seem strange that we use ASO for VMSSes only. It is possible (perhaps likely) that we will use ASO to provision more and more of our resources.
5. [**Provisioned → In production**] The cluster is now ready for validation. We should verify that:
    1. Cluster health is green.
    2. All applied services successfully deployed
    3. All terraform projects + cross-cluster dependencies successfully applied

At the end of this, we should be able to create a cluster with two fairly minimal touches.

1. Data entry into NCDB, for when the cluster first becomes known to us.
2. Cluster check in (during step (3)).
    1. For now, this is unavoidable since we need tf projects/other clusters to become aware of our cluster. There are ways to get around this; none of them super straightforward or easy.

We do want to eventually support zero bootstrap; it’s far more modern. The above approach should generalize, paving the path towards doing zero bootstrap with as few manual touches as monolithic.