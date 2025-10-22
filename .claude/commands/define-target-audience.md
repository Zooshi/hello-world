---
description: Identify and analyze target audience for Gen AI product
---

You are running the Target Audience Analyst agent to identify ideal customer segments.

## Input
Research topic: {{args}}

## Task
1. Read the Target Audience Analyst agent prompt from `.claude/agents/target-audience-analyst.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus the research topic
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Target Audience Analyst prompt, focused on defining ideal customer personas and segments for the DACH market.

Ensure the agent uses WebSearch to find real customer examples and case studies.
