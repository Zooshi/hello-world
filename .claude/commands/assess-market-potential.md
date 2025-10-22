---
description: Quantify Gen AI market potential and opportunity size
---

You are running the Market Potential Analyst agent to quantify the market opportunity.

## Input
Product/domain: {{args}}

## Task
1. Read the Market Potential Analyst agent prompt from `.claude/agents/market-potential-analyst.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus any available market research, target audience, and product strategy information
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Market Potential Analyst prompt, focused on calculating TAM/SAM/SOM for the DACH region.

Ensure the agent uses WebSearch for market size data and growth projections.

Note: This agent works best with input from Market Research, Target Audience Analysis, and Product Strategy.
