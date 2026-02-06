---
title: "oci"
---

- Quick Image Rollout and Replication ([@yacoub](https://openai.enterprise.slack.com/team/U09K6JT6MK8))
    - [@rrodan](https://openai.enterprise.slack.com/team/U030UJK9QFN) to provide more information here.
- Enhanced Network Counters and Visibility for Roma Inference ([@anniez](https://openai.enterprise.slack.com/team/U09MBNFHZNC))
    - Approx 90% already there, targeting next couple of week for delivery.
    - **Question:** What does 90% mean, and what is the remaining 10% / what are next steps?
- DC Inventory API ([@yacoub](https://openai.enterprise.slack.com/team/U09K6JT6MK8), will also impact returning RMAs [@anniez](https://openai.enterprise.slack.com/team/U09MBNFHZNC))
    - Estimated release 20-Nov-25
    - **Question:** Do we need any feedback and/or test cycles here?
- Unified capacity management (per fabric) within the pool ([@yacoub](https://openai.enterprise.slack.com/team/U09K6JT6MK8))
    - Meeting with the Eng team on Friday - moving forward
    - **Question:** What are we hoping to land on in terms of milestones and next steps on Friday? Seems we've been trying to get Engineering on it for ~3-4 weeks now so I am wondering what key outcomes we should expect before end of the year.
1. **Stable ID** -- the team is going to need a bit of time to evaluate this because we see it as a broader requirement than just an ID exercise. Jeremy suggested that this would be something good for us to talk through in more detail. I also got some inputs from [@yirui](https://openai.enterprise.slack.com/team/U07J4L32QG1) (Thank you, Yirui!) that I was able to pass back with the team.
2. **Dedicated Repair API** - The team is still working through those details as Dvij was describing on the call on Tuesday. We'll certainly keep you updated as that progresses and will likely want input from the team to make sure that it's meeting your requirements. In the interim,  [@pavihari](https://openai.enterprise.slack.com/team/U02V1UZ0BHR) shared the case template [here](https://amzn-external.slack.com/archives/C099DV7TWG1/p1762395549373689?thread_ts=1762395482.812939&cid=C099DV7TWG1) and you can use that with the Create Case API I shared to start to build some automation.
3. **Telemetry -** I synced up with Caroline on this piece and her recommendation was:
    1. For instance NV links, we'd recommend monitoring those in-band.
    2. For switch-to-switch NV links metrics, these are not yet available but on our roadmap. Depending on your willingness to provide feedback, we can explore a preview, but there aren't any public facing docs available as of yet.

Ya

⁠Ronak Pandya a 14 hour downtime is pretty disruptive and would require a bit of manual coordination between our two parties. we're shuffling capacity on our end and part of PHX60 hasn't fully scaled in yet, so it may help to do it in the next couple of days - or much later down the road. 

couple questions here:

- Can the team do this maintenance any earlier than 11/11? Can we do it tomorrow or next Monday?
- Can we shift the time window to avoid peak hours (after 10AM)
- On H100/H200 applied clusters we've been able to have rolling updates for CRD - what is the path to having rack by rack updates for FW on GB200s? 