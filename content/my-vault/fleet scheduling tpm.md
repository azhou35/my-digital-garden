---
title: "fleet scheduling tpm"
---

4 weeks
because imo I think when we (TPMs) get involved we tend to move really really fast because we can track and help ppl stay on top of shit

[4:17](https://openai.slack.com/archives/D09MD8VLL6P/p1761175074781269)

I imagine we can do this over the next 4 weeks

[4:18](https://openai.slack.com/archives/D09MD8VLL6P/p1761175093379039)

maybe weekly sync, concrete goals / milestones, and ez

Does the quota work from earlier interest you? I think we'll need someone from the team to drive it from a TPM perspective.  

- Make sure the ergonomics are good
- Expectations are managed
- Quotas are updated accordingly
- Users are sourced, interviewed, and trained

[3:51](https://openai.slack.com/archives/D09MD8VLL6P/p1761173518804019)

It's related RE: managing Hardware Health expectations per cluster so I figured it overlaps but want to get your feel on it.

  **Request for feedback**: **_Quota system simplification._** **_![:scheduled:](https://emoji.slack-edge.com/T03025Z7DT4/scheduled/8f6d5c06265dca7a.png)_**  
We're going to simplify how quota works by removing unintuitive features. Here is what we are proposing:**Before:** Non-critical priority jobs can overflow out of their targeted quota, not bound by the location the quota was restricted to.  
**After:** All jobs (critical or non-critical) need to target either ‘quota’ or ‘flex’. When targeting a quota, jobs will not leave that quota’s location restrictions, and will not be able to overflow outside of the quota**Before:** Availability capacity in Zoku / `brix capacity` shows all theoretical availability, including out-of-quota capacity at non-critical priorities.  
**After:** Zoku / `brix capacity` show in-quota and flex separately (e.g. run `brix capacity flex` to see unused GPUs in the cluster)**Before:** Sibling quotas can borrow from each other in case there’s unused GPUs, before overflowing out of quota.  
**After:** If there is capacity in a sibling quota, related quotas will be able to schedule in it - but this is separate from flex and will never go beyond the entire quota tree's availability.The single way to use unused GPUs in a cluster will be to target the `flex` quota that exists in each cluster and is the summation of all unused capacity across all quotas in that cluster. Jobs running on flex will be preempted by in-quota jobs being spun up. When scheduling on flex, the priority of your job only applies within your namespace, and namespaces are treated equally. We believe this new quota system will be much easier to understand for everyone - less confusion about why something doesn’t schedule, a clear path to finding free capacity across the fleet (just check flex!), and less edge cases for us to worry about when building the scheduling systems.Please provide your feedback about the current or proposed scheduling system to us in this thread ![:thread:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/apple-medium/1f9f5@2x.png). Once these plans are locked in, we will keep [#research-ah-announcements](https://openai.enterprise.slack.com/archives/C07CJT8J1H6) updated on progress rolling out these changes on a cluster-by-cluster basis.Sidenote: due to popular demand, we recently added support for access gating who can target your team’s quotas. If you also want to set this up for your quotas, please reach out to me and I can help you out! (edited)
