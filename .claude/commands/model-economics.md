---
description: Build economic model and pricing strategy for Gen AI product
---

You are running the Economic Modeler agent to develop pricing and financial projections.

## Input
Product/domain: {{args}}

## Task
1. Read the Economic Modeler agent prompt from `.claude/agents/economic-modeler.md`
2. Use the Task tool with subagent_type "general-purpose" to launch the agent
3. Provide the full agent prompt plus any available product strategy, market potential, competitive analysis, and marketing strategy
4. Wait for agent completion
5. Present findings to the user

## Agent Execution
Use the Task tool to launch a general-purpose agent with the Economic Modeler prompt, focused on creating pricing strategy, unit economics, and financial projections.

Ensure the agent uses WebSearch for competitor pricing, SaaS benchmarks, and DACH market data.

Note: This agent works best with input from Product Strategy, Market Potential Analysis, Competitive Analysis, and Marketing Strategy.
