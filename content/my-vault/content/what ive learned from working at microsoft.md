---
title: "what ive learned from working at microsoft"
---

Write about what you’ve learned by operating inside Microsoft’s AI supercomputing organization.

- **Start with what you observed.**  
    What did this environment teach you about how large systems sustain themselves — the incentives, rhythms, and hidden architectures that make them work (or stall)? What patterns of coordination, ownership, and decision-making did you come to understand?
    
- **Then reflect on your growth.**  
    What skills or instincts did you sharpen most — technical, operational, or interpersonal? What surprised you about yourself? What constraints shaped you in productive ways, and which ones dulled your edge?
    
- **Examine the system itself.**  
    Where did you see strength — in culture, collaboration, or clarity? Where did tension or friction emerge — between speed and safety, between autonomy and alignment, between ambition and bureaucracy? What opportunities for evolution did you glimpse that the organization wasn’t yet ready to take?
    
- **Finally, look forward.**  
    What do you want to carry with you — the principles, habits, or questions worth preserving? What do you hope to unlearn? As you move to OpenAI, what kind of builder, partner, and leader do you intend to become?

the first time i heard about a gpu was my sophomore summer, when my manager handed me a six-pound alienware laptop. it was overkill for a technical writing intern, but i was on the gaming team at aws and needed to load up unity. my intern friends begged that i lend it to them so they play league of legends at 160 bps. i shrugged it off and barely used it because it was so heavy to carry around. 

today a gb200 can eat up to 3M per 72-GPU rack. and in my first job out of college, i would work with over 10k of them in a supercomputer. 

i joined microsoft at a time that was extremely pivotal to our partnership with ai companies (openai, bytedance, mai, etc).  i bore witness to some of the greatest strengths and weaknesses to a generational company. 

my team started out as a burgeoning [hpc]([differences between AI and HPC](https://www.glennklockwood.com/garden/differences-between-AI-and-HPC)) software provider in the 2010s, and found itself well-positioned to provide the compute experience during the ai wave. i've witnessed the team make a full transition from a product org to a capacity planning function. i joined expecting to drive a compute strategy for a new product division (biology) and instead fell into a world where we were laser-focused on one customer. 

when you're in between a frontier startup customer and a ginormous company, you are squeezed from both ends: balancing speed with safety, progress with reliability, 

to feed a gpu-hungry industries, hyperscalers have the raw compute and the reputation. but when you are a generalized battleship with roots in the cloud, it makes you ill-equipped for AI workloads. [neoclouds]( [AlphaSense on X: "Former $NVDA employee reveals $NVDA's strategic shift toward neocloud partnerships ( $CRWV, $NBIS, $AMZN ): - According to the expert, neoclouds are preferred for AI workloads because their infrastructure is purpose-built for high-performance computing. Unlike hyperscalers, https://t.co/Kj78IgbqUW" / X](https://x.com/AlphaSenseInc/status/1976281549621338535) ) that are purpose-built for AI have seen considerable results.

i also saw the hints of the partnership fraying, especially as openai diversified their compute providers and microsoft built out its internal microsoft ai team - it's a business move to [outsource]([Rihard Jarc on X: "An interview with a former OpenAI employee that came over the weekend, confirming my hunch, which I already wrote about in the article last week, that the biggest friction between OpenAI and $MSFT is around infrastructure capacity: 1. OAI requests were "leading to massive https://t.co/ELAAAkPVco" / X](https://x.com/RihardJarc/status/1977743106997928445)) some of the compute capacity to other providers and offset some of the risk for microsoft itself.

**org culture**

as a technical pm, i learned my job was really about *outcomes.* to drive forward a workstream is inherently managing a variety of stakeholders, all with varying relevance of real influence over your program. the role of a tpm is to thread the needle within organizations and find the highest leverage item to do. 

it's a customer-facing role, but you really focus on one or two key accounts. typically the ic tpms would focus on various customers and cover ground on different domains (weather / finance /biology) and a manager would drive the strategy for the product. 

there are gates everywhere - friction in getting permissions to access data, to accessing the notes of a program, to getting a simple kpi through. this is because we are an organization that prioritizes reliability and security and any sort of risk is disastrous. 

you need an advocate for you at work. the best way to do this is through execution and to find other people who had chances taken on them when they were young, and i am extraordinarily lucky to have mentors who spotlighted me.

too much complacency breeds executive dysfunction. 

at its best, microsoft incentivizes extreme diversity of folks with niche knowledge, especially when it came to the 100+ domains involved in running a supercomputer. however, it also means people could be wildly protective of their scope. 

transparently, microsoft only operates well as a hybrid company due to the sheer size of the company, but this is also its huge limitation. 

#### tpm <> dev relation 
from college i wanted to be a product manager and fell more into tpm. a rule of thumb of a pm is to define the "why" and tpm is about the "how", but the more natural role of tpm in my org is because we had become less of a product-driven org and more of a hardware/capacity planning one. 

a friend once commented a pm has a bird's eye view of an org, keeps a pulse on org-wide politics. i believe a pm runs up and down the [[content/ladder of abstraction|ladder of abstraction]] and therefore need to be highly autonomous (while still holding dependencies on all of their related teams.)

this is uniquely difficult and necessary at microsoft because of the remote-first culture, the wide company size, the preference for stability, among others. 

a tpm is intended to make a dev's path from 0 to 1 as seamless as possible. this manifests through building automations, driving processes, managing customer interactions - but can also fall into the trap of clicking slides and culling emails. 

i'd describe many of the devs i had close relationships with as [site reliability engineers]([Google SRE - Site Reliability engineering](https://sre.google/)), where the philosophy is to embed operations as a software problem.
#### skills

i learned to negotiate, to push back, to dig into data and dependencies, to "double-click," to tame a ferocious customer. i learned that any statement needs to be backed by data/trends, and that the best decisions are guided by observations. 

at the same time, i learned some complacent behaviors. calendar jenga meant that cross-functional partnerships could limp forward weeks on end. a clearly defined hierarchy means if you wanted to enlist a team to work with you, you had to go from the top and clear it with the manager. 

the most frustrating was trying to build something that would facilitate early return of a cluster to openai - i literally had six calls where i started with karthik who redirected me to anvil to onedeploy to crd to onedeploy all the way back to karthik. people just are not incentivized to make changes and that's a natural consequence of a heavy-weighted industry. 

in my new chapter as a tpm on the gpu fleet team, i anticipate it'll take my previous experience on hard mode - a focus on taking an automation from 0->1, pressuring partners.

i hope to adopt a mindset that shifts from avoiding the worst case to optimizing for the best case. 

list of things (inspired by)