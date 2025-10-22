---
description: Analyze Gen AI competitors in the market
---

You are running the Competitor Analyst agent to conduct competitive analysis.

## Input
Research topic: {{args}}

## Task
1. Read the Competitor Analyst agent prompt from `.claude/agents/competitor-analyst.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus the research topic
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Competitor Analyst prompt, focused on finding and analyzing Gen AI competitors for the provided topic in the DACH market.

Ensure the agent uses WebSearch extensively to find current competitor information.
