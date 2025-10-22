---
description: Develop Gen AI marketing and go-to-market strategy
---

You are running the Marketing Strategist agent to develop marketing and GTM strategy.

## Input
Product/domain: {{args}}

## Task
1. Read the Marketing Strategist agent prompt from `.claude/agents/marketing-strategist.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus any available product strategy, target audience, market potential, and competitive analysis
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Marketing Strategist prompt, focused on creating a comprehensive marketing plan for the DACH market.

Ensure the agent uses WebSearch for DACH marketing best practices and benchmarks.

Note: This agent works best with input from Product Strategy, Target Audience Analysis, Market Potential, and Competitive Analysis.
