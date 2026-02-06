---
title: "codex hackathon helpful links"
---

app garden - take a codebase to deploy it for anyone to use
- https://openai.enterprise.slack.com/docs/T0BQTNSUF/F09LT2PMC1W
Come show off what kinds of crazy things you can get Codex to do! From vibe research to debugging live distributed systems to plain-old building big stuff!
We're hoping this will be an opportunity to:
see how far you can push Codex to do complex work e2e – whole research workflows, full-stack app development, cluster management, …
build shareable / reusable skills and tools for Codex which will carry back into our normal work
experiment with new ways of harnessing / scaffolding / prompting the model to get it to do more
for people who haven't tried Codex recently (shame on you), to spend some serious time trying it and feel the AGI

ideas:
	- dc management
		- https://openai.enterprise.slack.com/archives/C0A9CV4QBQC/p1768927554911989

Idea: 
- Maintenance Ingest workflow
	- Trigger way to 
		- clean up data to make it a primary key
		- Add new maintenances via human input 
			- Script that asks for quetons 
		- oak-ro-snowflake - queries snowflake! This one you'll need to export your SNOWFLAKE_USERNAME and SNOWFLAKE_PASSWORD.
If you want your personal svcact-<you> for programmatic Snowflake access1) Check if it already exists by trying to use it:   • set SNOWFLAKE_USERNAME=svcact-<your_username> and run am reset-snowflake-password (this commonly resets the svcact- account) [6]2) If you don’t have one / it doesn’t work, the “creation” path is basically:   • ask in the Snowflake access/support channel (e.g. #applied-snowflake-access) or file an IT ticket and ask for a svcact-<you> Snowflake user + appropriate roles/warehouse grants. The admin-panel phrasing shows up in practice [2], and IT gets pulled in for account state changes [3].

frontend-designer + figma-* skills 
linear-implement-ticket

pagerduty-inciden111t

slack-thread-reader