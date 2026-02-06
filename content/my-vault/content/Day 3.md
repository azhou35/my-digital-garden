---
title: "Day 3"
---

*Maintenance Alert - Clusters: c221, c254, c259, c273*

===================================================

These clusters will be quarantined and capacity temporarily removed for critical maintenance. Please confirm if your engines can take this downtime, or if you need backfill capacity. Engine groups losing >25% capacity are marked with :ashui-alerte:

  

*Maintenance Date/Time: <INPUT_TIME_RANGE>*

  

*Impact Summary:*

===================================================

- Codex - 941 a100e - 2 engine groups - max group impact: 30%

- ImageGen - 928 a100e - 3 engine groups - max group impact: 38%

- ChatGPT - 480 a100e - 2 engine groups - max group impact: 28%

- API - 368 a100e - 4 engine groups - max group impact: 100%

- Search - 259 a100e - 1 engine groups - max group impact: 17%

- Enterprise - 96 a100e - 1 engine groups - max group impact: 41%

  

*Impact Detail:*

===================================================

*Codex — Total: 941 a100e - @codex-oncall*

• codex-api-251113 - 845 a100e - 30% of engine group - cluster(s): c221, c259 :ashui-alerte:

• codex-api-250915 - 96 a100e - 16% of engine group - cluster(s): c221

  

*ImageGen — Total: 928 a100e - @image-gen-service-oncall*

• ig-3p-p-edit6 - 434 a100e - 38% of engine group - cluster(s): c254, c259 :ashui-alerte:

• ig-1p-1205-udec-2 - 216 a100e - 32% of engine group - cluster(s): c254, c259 :ashui-alerte:

• ig-3p-p-gen4 - 278 a100e - 18% of engine group - cluster(s): c254, c259

  

*ChatGPT — Total: 480 a100e - @chatgpt-infra-oncall*

• gpt5-fpyd-rm-0807 - 384 a100e - 28% of engine group - cluster(s): c254 :ashui-alerte:

• gpt5n-chat-251029 - 96 a100e - 17% of engine group - cluster(s): c254

  

*API — Total: 368 a100e - @api-infra-oncall*

• gpt5-visible-cot - 46 a100e - 100% of engine group - cluster(s): c221 :ashui-alerte:

• gpt5n-0804s170 - 72 a100e - 44% of engine group - cluster(s): c221 :ashui-alerte:

• gpt-41m-ft-or - 96 a100e - 18% of engine group - cluster(s): c221

• o3m-api-250131-3 - 154 a100e - 17% of engine group - cluster(s): c221

  

*Search — Total: 259 a100e - @search-oncall*

• gpt4o-sonic-api - 259 a100e - 17% of engine group - cluster(s): c221

  

*Enterprise — Total: 96 a100e*

• emb-bab-v3-dr8-eu - 96 a100e - 41% of engine group - cluster(s): c259 :ashui-alerte:

