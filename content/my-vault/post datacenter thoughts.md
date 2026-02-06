---
title: "post datacenter thoughts"
---

denton - 30 min from texas
everything is bigger in texas

i've never been to texas - everything truly is bigger. for dinner we get massive entrees of fish laden in butter and a greek salad with an entire block of feta. beer comes in a heavy chalice, fit for a medieval prince. the rental car we get is a kia. dfw resembles a heart, with several ventricles and connectiosn to the rest of america. 

id imagine in a place with such abundance, it is very easy to believe in a god that granted us this gift. that you simultaneously find purpose in driving down the road and tending to your land, that you are feasting from the land you live on. 

**why texas?**
- practical - tax benefits
	- Texas [offers a sales tax abatement](https://comptroller.texas.gov/taxes/data-centers) on equipment and electricity for data centers that are at least 100,000 square feet, invest at least $200 million and employ at least 20 people at above-average wages from the county where the data center is located, according to the state comptroller.
	- space
	- power grid
		- The council’s decisions in August and November have come at a time when experts [are warning that Texas’ power grid faces](https://www.npr.org/2024/06/21/nx-s1-5002265/texas-power-grid-is-challenged-by-electricity-loving-computer-data-centers) new strains from a growing tech sector of data centers for AI computing and crypto mining with expectations to consume record levels of energy.
i wonder what is like to see this open space used for something so incomprehensible, somethign ununderstandable. 

if the airport is the heart we were doing a short drive to the brain, a gpu datacenter.

in our trip to texas my coworker insists we go to buckees. im from jersey so i udnerstand the cult lov for a grocery store it must be like nj. 

we go to buckee's which is the classic hallmark of americana - they are carving meats in the middle and there are gas station stalls for days. at some point they stop and recite a pledge. there is packaged banana pudding and buckees nuggets (which someone mistakenly refers to as nuts) and wall of beef jerkey, next to a meat counter of choose your own jerkey.
gas is $3 and no one is at the station. if you wander past the cute animals there is a section reserved for guns. it's a combination gas station grocery store.

wild west shutdown except its group of silicon valley engineers vs local dc techs. i am grateful for this opportunity for perspective. 

when my parents immigrated to america they expected the plains of virginia, the country roads. 

a beaver stares at you from pajama pants, from towels, from water bottles. truly if there is a need there is a object, and even if there is not a need one is invented. 

there are details of which i cannot describe in detail 

infrastructure is the backbone of this economy. the brain of america may exist at the coasts but the veins exist in the railroads, datacenters, and factories. 

i wear steel toed boots to save space in my backpack, which means they alert the security when i pass through, twice. i dither at my closet door, unsure what to wear - will it be cold? warm? construction worker fashion chic? i settle on a jean jacket and flared leggings to pair with the timberlands i expensed for this trip. 

there is a certain swagger i cannot plan for. 

but there is publicly available information 
in a way visiting a dc feels post-economic 

you go into a room with this many coreweave folks and you realize everyone makes so much money 

there are stickers on their hard hats, inside jokes im sure they made over a pint of beer.
lots of jeans, swagger, flannel

who are the people building the data centers? 
these dc techs - it's hard work, to switch out a r ack is 30 pounds. 

in a way it is a computer that is so large in scale it needs humans to manually replace thigns

a coworker comments that the price of external hard drives have gone up bc of the demand for ssds, which store information for the model weights. given the choice of a photo of your cat vs the entire catalog of the internet since the 80s, what would you pick? 

**to explain a gpu:**
nvidias nvl72 is a system of 72 nodes, aka 8 racks, connected to 8 nvl racks. it comprises of cpus which do more high-paced low storage work. fiber networking connects these racks to each other within a row, which in turn communicates across an entire ib fabric. 

**to explain a datacenter**

- its a herculean physical undertaking 
- just construction wise - foundation piles, structural steel, underground cables, mechanical pipping
- extremely fast networking, fast connections
there are hundreds of wires metculously ziptied together.
behind them they are connected to a power source, which are thick knots of wires.

these salient physical features of a gpu evolve from engineering constraitns and needs for throughput, speed, latency, and power.


i think of the scene of the matrix when humans are connected to these huge computers via wire.

what are the neighboring effects
- are most data centers colo w the power plants - most of neighboring community impact comes from pwoer generation and not data cente ritself - does dc itself have cooling needs and water needs 
- - internet concerns about water needs - but data center is not as substantial % 
- a lot of real estate construction startups are all like data center construction - who are the blue collar ppl who are in demnad to build all the data centers and transmission nad power plants
	- what would it take for american tehc workers to go back to these jobs instead of idolizing our shinty 9 - 5 
- are dcs bringing back factory towns?
we talk a lot with the leadership and program managers who own the data center, less so the actual workers who work there. there is soemone filing a jira ticket with hsi laptop open. 
there are no chairs so they sit on the ground to type on their computer
there is a back room where dell actually services and repairs the racks. 

it actually takes way more technicians to build up a datacenter vs service it. 
this is such a specialized skill that its hard to hire for. 
i wonder how dc techs hear about these jobs - there are many signs in russian and apparently there is a consultancy of russian dc techs woh can do the job efficiently

i think we react so defensively to data centers bc we are already so desniized to the infra needed for the cloud. even to operate an website or app that connects to aws, ur talking about investments in the orders of millinos. to build your phone relies on supply chain sophistication across huge factories with little to no min wage.
but then again, cloud runs many independent workloads at once, whereas an ai datacenter serves as one large computer.
i wonder why we do not react to this with the same awe we give to a skyscraper, which equally uses as many resources and takes up as much as space. maybe because it is a blight in an otherwise void of vastnesss - maybe bc it doesnt provide sanctuary for humans but rather nodes - maybe because we are awed by vertical height but its the horiztonal vastness that scares us. 

i am writing this bc there is power in knowledge 

look at your computer. imagine every time you rebooted your macbook because someone was restarting someone had to physical walk down the aisle and power evertything off. 

this is a story that is deeply american built on eastern technology.


there are fans from the gb200s that means that i cannot hear whats going on. 
back at my old job, i interacted with dc techs only via teams call. 

we open a gpu tray but the coveted nvl tray is seaeld shut, with the only way to service by senidng back to nvidia. trade secrets, im sure.  it reminds me of how we cant open my iphone to fix it.

i imagine there is something about having a physical hardware piece of technology that lures people into this field of work, akin to fixing up a car or being into boats and transportation. an old boss cited video games and taking apart gaming computers as what led him to his work. 
the same way the texans are proud of their cars, or the people of the war took apart radios to understand how they work. every generation there exists some hardware that fascinates us.

what would it be like to go to a chip factory, where you fabricating something at the dimension of nanoseconds?

at home my sister shows me her gpu that she ordered online. its about a k and feels plastic and cheap despite weighnig 5 pounds. the chinese just dumped some expensive gpus insdie a shitty cover, we say. we train a local model (llama iii) and try to fine tune it. "recommend a korean restauratn to us"

i think for me it was a loose fascination with space and rockets. 


the gb200 is a beautiful beast. 
72 NVIDIA Blackwell GPUs, tied together in a single NVLink domain that delivers 1.8 terabytes of GPU-to-GPU bandwidth and gives every GPU access to 14 terabytes of pooled memory. Rather than behaving like dozens of separate chips, the rack operates as a single, giant accelerator, capable of processing an astonishing 865,000 tokens per second
networking topology - NVLink and NVSwitch at terabytes per second, collapsing memory and bandwidth barriers
Azure uses both InfiniBand and Ethernet fabrics that deliver 800 Gbps, in a full fat tree non-blocking architecture to ensure that every GPU can talk to every other GPU at full line rate without congestion
we drive into an undescripit area that defies description - 
want to ask - what 
coreweave 

im curious by this and the car factories, and how they implement jit adn kaizen 
the intricaties has increased exponentially - its not going down a chain but there is an intricate dance to every operation 

we look thru several rooms
- the gpu room there is a security check before you can enter 
- its dark 
- the nodes glitter and pulse like emerald eyes in a cave 
- each rack weighs XX pounds 
- they tell us about the facility but my ears are muffled, so trying to understand is like answers a fill in the blank question when you dont know the options 
pretty dark 

260 MW of power
- each building has ~40 of rows, with each row having 8 racks
- they also have 7 spare warm racks (the last row) in each building they use for spares and triage
- the rows are labeled <building letter><2 digit row number><rack index>, which is a very nice schema and maps neatly onto ours (we'd just replace the letter with the corresponding number)
- they're also adamant about calling them nvlink domains, not racks (just like our scaleup domains)
- ear protection was mandatory and everyone inside was wearing some form of it. They were pretty adamanant about this and mentioned OSHA. Big constrast with OCI.
- pretty neat cabling overall
- they use trunk cables between buildings, but use standard fiber inside a building.
- they're moving (seemingly quickly) from smc to dell for odm. Not a total switch but they seem to really prefer dell. The stated benefits are much stronger partnership with dell than smc, and more control over both repairs and provisioning than smc is willing to give them
- - the average knowledge level of a cw tech on the floor seemed astronomically high 
- compared to other places I've seen

growing up i felt a snese of disgust passing by the factoreis between nj and nyc which felt like economic deadzone

theres a symbolic malaise to factories and datacenters, even if they arguably produce higher economic output than ashiny 

dc tech 
- turn on/off gear, replacing hard drives, servicing
- rack and stack - manual labor
- cabling - incredibly tedious 
- low level config tickets 
- higher level config
- network engineering setup 
- cable up full racks 
- cable hell
	- https://www.reddit.com/search/?q=cable+hell+data+center&cId=b024c70a-181b-4f93-8d74-d3e354d7c7f5&iId=8aa75bf7-2e01-4c98-a6c2-5849a991839a
- Loud. Cold. Hot. Spaghetti maze. Heavy servers on bottom, lighter ones at top-SIKE, switch it around. Why is this UPS beeping
- there are not that many permanent jobs - its ilke cleaning or security
- a big job is actually security
3 sys admins, 2 NOC operators, 1 CTO/CIO. 1 deckhand working 5/7, 9-5. External security company with 12 posts on property in total. I don't remember if those 12 were manned all the time. 2 cleaning ladies (external). 1 maintenance guy
- sitting around witing for something to break 
- One guy at the top of the food chain lives 5 states away, 5 guys make $20/hr running around repluging shit and replacing parts mindlessly. data center is not that much different that say a high tech manufacturing plant. Electrical and mechanic people , some IT ops but it’s pretty low man power operations
- Being a tech in those places is to rack and stack server & network equipment. Open boxes, unpack, plug in cables. Next!
- All the actual setup is handled by designated sys admins (mostly offshore).

prime real estate for housing 
- but A lot of these new data center areas are on plots of land that are not zoned for residential and would not be zoned for residential.
Plus the rezoning process can take many months to years and most developers aren’t going to pay taxes on a piece of land that long just to be told the County decided not to rezone it anyways because it doesn’t work with their master plan.
Exact opposite, the datacenters bring in large amounts of money that allows Loudoun to have such nice schools, parks, very low property taxes, and the Sheriffs do not need to use tickets to makeup for budget shortfalls. Of course Loudoun also manages its datacenter development with a long term plan and has been doing so for something like two decades.


the economic output of a data center is difficult to discern. on one hand you'd imagine that it's the same as factories - invest millions and you net jobs for thousands of locals. the reality is a bit more complicated - it's not like a factory where each square foot is used by a worker, but rather more like a zoo where one person is walking up and down the hall to make sure the lions aren't fighting each other. 

look to loundon as an example of an area with positive impact. data center taxes pay for 38% of Loudoun's general fund. By sq/ft they bring in the most taxes of any industry. The next best industry is hotels and you would need 8 datacenter sized hotels to bring in the same taxes as one datacenter. 

https://www.reddit.com/r/nova/comments/1pezsl7/the_data_center_resistance_has_arrived/
