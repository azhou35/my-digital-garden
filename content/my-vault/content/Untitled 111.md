---
title: "Untitled 111"
---


227, 248, 253, 263, 290, 293, and 294 
Heads up that we're planning on doing a maintenance outage for c227 to do a control plane + node upgrade in one shot.
This is coming down the pipeline sometime this week or next. Will give a couple of days lead time, but I suspect that this shouldn't be too disruptive given that there are presently  <1k scheduleable gpus on this cluster.
Yeah, we can start a pre-emptive sev for that. We may also end up doing a similar thing for c248 depending on some derisking exercises I'm doing right now, but we'll see.

Best case scenario we get c248  slow-rolling over the weekend with a small buffer. Worst case we do a quick hard cut over of that cluster's capacity.

c293 and c290 are canarying the change right now. I don't see issues and am slow rolling it out with minimal capacity implicationsc294 will be rolled out gradually but relatively quickly (over the course of a few days) unless we hit a snag and need to call maintenance on those, but I suspect those will just be rolling with minimal capacity hits to actual workloads and don't require any sevs.I suspect these three will be fully migrated come MondayI'll have baked the new image for about 24 hours come this afternoon, and in turn may want to slip into the rollouts for c263 and c253 as they are happening. I may need to continue to do some updating on whatever hasn't received the image afterwards. Chatted with @dyli about this and we think this is fine as long as we have derisked my change elsewhere in GCP.