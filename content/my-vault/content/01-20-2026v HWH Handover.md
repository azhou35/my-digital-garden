---
title: "01-20-2026v HWH Handover"
---

## HWH On-Call - 2026-01-21

1. Standardizing APIs
	1. What should our response formats and requests look like for APIs that we need across all CSPs.
	2. What are the right scale-up domains to think through
	3. What operations do we need?
	4. Single-Node operations
	5. Whole-Rack operations
	6. What other abstractions do we need?
	7. What happens if we sign another provider tomorrow? What do they need to build for us and close gaps on instead of us just saying "okay we will turn it on?"
2. Every GB300/IB XDR fabric is broken :(
	Switch issue, AIs on NVIDIA (New switches)
	F28, F29, F30, F33 IB (step time doubled)
	larger = worse (f33)
	can be mitigated [by Azure] but breaks again
	AI: consider detection
3. AMD (MI300x) in bad state William Sheu
	1. Chromium bleeding/spewing garbage
4. Maintenances resulted in a lot of alerts
	1. Process for cluster state change => muting alerts not followed
5. Turnups/maintenances
	1. Very costly in term of human toil
	2. Manual fabric validation
	3. Firmware and driver versions and stale across the fleet
		1. => increase homogeneit
		2. Node naming is pain [id_node]
		3. Expectations on handoff not super clear



