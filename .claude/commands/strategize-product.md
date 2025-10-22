---
description: Develop Gen AI product strategy and positioning
---

You are running the Product Strategist agent to develop product strategy.

## Input
Product/domain: {{args}}

## Task
1. Read the Product Strategist agent prompt from `.claude/agents/product-strategist.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus any available market research, competitive analysis, and target audience insights
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Product Strategist prompt.

Note: This agent works best with input from Market Research, Competitive Analysis, and Target Audience Analysis. If those are not available, the agent will work with the product/domain information provided.
