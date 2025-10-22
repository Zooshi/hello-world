---
description: Run comprehensive Gen AI product research with full expert team analysis
---

You are orchestrating a comprehensive Gen AI Research Team to analyze a product opportunity for the DACH market (Germany, Austria, Switzerland).

## Input from User
The user has provided: {{args}}

This could be:
- A specific product idea (e.g., "AI-powered legal document analyzer")
- An industry/domain (e.g., "healthcare AI solutions")
- A rough concept (e.g., "Gen AI for German SMBs")

## Your Mission
Coordinate a team of expert agents to conduct thorough research and produce a comprehensive report covering:
- Market analysis
- Competitive landscape
- Target audience identification
- Product strategy
- Market potential quantification
- Marketing strategy
- Economic modeling

## Execution Process

### Phase 1: Parallel Research (Run these 3 agents in parallel)
Launch these agents simultaneously using multiple Task tool calls in a single message:

1. **Market Researcher Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Use the full prompt from `.claude/agents/market-researcher.md` + "Research topic: {{args}}"

2. **Competitor Analyst Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Use the full prompt from `.claude/agents/competitor-analyst.md` + "Research topic: {{args}}"

3. **Target Audience Analyst Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Use the full prompt from `.claude/agents/target-audience-analyst.md` + "Research topic: {{args}}"

**IMPORTANT**: Run all three agents in parallel by using three Task tool calls in a single message.

### Phase 2: Sequential Strategy Development (Requires Phase 1 outputs)
After Phase 1 completes, run these agents sequentially:

4. **Product Strategist Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Full prompt from `.claude/agents/product-strategist.md` + Phase 1 findings

5. **Market Potential Analyst Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Full prompt from `.claude/agents/market-potential-analyst.md` + Phase 1 findings + Product Strategy

### Phase 3: Parallel Tactical Planning (Run these 2 agents in parallel)
After Phase 2 completes, launch simultaneously:

6. **Marketing Strategist Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Full prompt from `.claude/agents/marketing-strategist.md` + all prior findings

7. **Economic Modeler Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Full prompt from `.claude/agents/economic-modeler.md` + all prior findings

**IMPORTANT**: Run both agents in parallel by using two Task tool calls in a single message.

### Phase 4: Final Synthesis
After all agents complete:

8. **Research Coordinator Agent** - Use Task tool with:
   - subagent_type: "general-purpose"
   - prompt: Full prompt from `.claude/agents/research-coordinator.md` + all agent outputs

The coordinator will:
- Review all findings
- Facilitate inter-agent critique (max 2 iterations)
- Synthesize comprehensive report
- Identify consensus and open questions

## Implementation Steps

1. **Read all agent prompt templates** from `.claude/agents/` directory
2. **Execute Phase 1** (parallel): Launch 3 agents simultaneously
3. **Wait for Phase 1 completion**: Collect all outputs
4. **Execute Phase 2** (sequential): Launch agents one after another
5. **Wait for Phase 2 completion**: Collect outputs
6. **Execute Phase 3** (parallel): Launch 2 agents simultaneously
7. **Wait for Phase 3 completion**: Collect all outputs
8. **Execute Phase 4** (synthesis): Launch coordinator agent
9. **Generate final report**: Save as markdown file in project root

## Output Deliverable
Create a comprehensive markdown report named: `gen-ai-research-report-[timestamp].md`

The report should include:
- Executive summary
- All research findings organized by section
- Visualizations (mermaid diagrams where appropriate)
- Action items and recommendations
- Clear GO/NO-GO/CONDITIONAL recommendation
- Risks and mitigation strategies

## Important Guidelines
- Use WebSearch extensively through agents for current, accurate data
- Focus all research on DACH market (Germany, Austria, Switzerland)
- Ensure agents critique and reach consensus (max 2 iterations)
- If conflicts remain after 2 iterations, document them in the report
- Run agents in parallel wherever possible for efficiency
- Each agent uses Claude Sonnet 4.5 (via general-purpose subagent_type)
- Provide progress updates as each phase completes
- Save final report to file

## Success Criteria
- [ ] All 7 specialist agents have completed their analysis
- [ ] Research Coordinator has synthesized findings
- [ ] Final report is comprehensive and actionable
- [ ] Report saved as markdown file
- [ ] User notified of completion
