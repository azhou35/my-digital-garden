---
title: "12-16 azure hpc - gpu weekly sync"
---

issue with scottie - trying to repo nodes
Dilip - cannot repro the issue

2.2 in end of January / February 

sig change from 1.3 to 2.2 
keep automation on their side
do bmc upgrade on their side 

az-net issue if u have a lot of traffic going thru the private end point
not a throughput limitation
either it is a backend service w a limitation
or an az net exhaustion if someone is hitting limitation 
need to understand source, destination, load balancer 
where is the customer seeing a limitation
backend is a kubernetes cluster 

1) 50gps is a 

bandwidth issue not latency 
either is 

no bottlenecks here 

is it client having throttling or server throttling
no one can finish tasks bc network is too slow 
we ask ppl to turn off their tasks 
improves the network performance for everyone else 
when they retry causse more 
reduced load 

env | grep JIRA
