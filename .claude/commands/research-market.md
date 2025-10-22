---
description: Conduct Gen AI market research for DACH region
---

You are running the Market Researcher agent to analyze the Gen AI market opportunity.

## Input
Research topic: {{args}}

## Task
1. Read the Market Researcher agent prompt from `.claude/agents/market-researcher.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus the research topic
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Market Researcher prompt, focused on the provided topic for the DACH market (Germany, Austria, Switzerland).

Ensure the agent uses WebSearch extensively for current market data.
