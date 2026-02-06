---
title: "12-01 diary entry"
---

i feel quite tired this week
emotionally exhausted from corporate socializing and feeling out of place and not funny and not smart 
feeling a little tired of talking about new york and missing new york
my writing feels insufficient 
and forced
as if i had not written something good in a while
it is cold in sf but not that cold.
my spotify wrapped was not that interesting
my taste buds are picky now
v/j had such aura at our holiday party. they seemed like such a good couple.

y seems to be killing it at work. he chats w ppl in person all the time and also made a script he told kenny about. sometimes i wonder why i bother going into office

i am tired of going to museums
but my heytea was very yummy 
i feel very messy and gross here 
i feel like hwh team is not as close-knit as the clusters team
i sit further from them so i feel less connected
i should try to get to know them better
kenny taught me about the tensor weight api and the clusters IOPs thing and how google delivers it to us with it condensed
melissa taught me about suasage link and how it rides the backbone of cp / other providers in order to connect everything eventually to an azure connection
-> eventually to be replaced by big noodle

melissa is so friendly w everyone. like vishal and kevin and kenny. i wonder how she does it. she was so good at explaining things to me and seems very confident. 

i wonder why i am not great at socializing. im only 6 weeks in? 
i usually skip out on lunch and dinners just to eat meals by myself. whenever i eat with people i dont get to say much to them
my work still feels un poco siloed. even though i am supposed to lean in with other people to solve problems. 
kenny says im doing good work but i fear that once maintenance gets sorted out what will i really do. like how do i uplevel my work here. 

why do i feel so tired especially this week? work itself was not that bad 

dislocation
am i introverted ? i overthink so mcuh

Hi all, heads up on a change coming in allocation coming to improve the predictability of allocated GPUs and address overallocation :froge-over-allocated:

Historically, we planned and allocated nearly the full cluster capacity in Zoku, which did not align with how cluster health SLAs are defined and operated. When some GPUs became unhealthy, a team’s full quota may not be actually available, which led to jobs not scheduling as expected. In practice, we had over-allocated clusters, making it hard for researchers to reliably plan training and evals that depend on expected number of GPUs.

Starting with the next compute shuffle, which will land in the next week or so, we will plan quotas based on healthy, within-SLA GPUs per cluster. This ensures that even when some GPUs are unhealthy, there is still enough capacity to support all tenants. Any additional healthy GPUs above the SLA will still be shared to teams so they can benefit from extra capacity when it’s available!

Example:
A cluster has 100 GPUs with an SLA of 85 healthy GPUs. We will binpack teams up to 85 GPUs (e.g., Team A: 30, Team B: 55). In Zoku and b-capacity, teams may see slightly higher expected numbers (e.g., Team A: 35, Team B: 64), this is to enable:
If up to 15 GPUs go unhealthy, teams are not impacted.
If health drops below SLA, Hardware Health will work to restore it.
If more than 85 GPUs are healthy, the extra capacity is distributed to teams because the setting in Zoku is higher.

From an accounting perspective, the adjustment may make the overall Compute seem lower, but they should now reflect stable, realistic compute you can actually rely on. These targets match what we consistently maintain today based on historical data. For questions or support, feel free to reach out to @fleet-tpm :froge-heart:

Hey all! Heads up that we’re improving compute planning to address overallocation and improve the reliability of allocated GPUs

We’re making an improvement to compute planning to address overallocation, which has sometimes made GPU availability appear higher than what’s actually schedulable for research workloads.