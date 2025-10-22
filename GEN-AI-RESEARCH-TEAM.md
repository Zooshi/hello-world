# Gen AI Research Team

A sophisticated multi-agent research system built for Claude Code that conducts comprehensive market research, competitive analysis, and strategic planning for Generative AI products in the DACH region (Germany, Austria, Switzerland).

## Overview

This system orchestrates a team of 7 specialized expert agents that work together to analyze Gen AI product opportunities and produce actionable research reports. The team includes:

1. **Market Researcher** - Analyzes market landscape, trends, and opportunities
2. **Competitor Analyst** - Deep-dives into competitive landscape and positioning
3. **Target Audience Analyst** - Identifies ideal customer segments and personas
4. **Product Strategist** - Develops product strategy and differentiation
5. **Market Potential Analyst** - Quantifies market size and revenue projections
6. **Marketing Strategist** - Creates go-to-market and customer acquisition plans
7. **Economic Modeler** - Builds pricing strategy and financial models
8. **Research Coordinator** - Orchestrates the team and synthesizes final report

## Key Features

- **Hybrid Execution**: Runs agents in parallel where possible, sequentially where dependencies exist
- **DACH Market Focus**: All research targeted at German-speaking countries
- **Web-Powered Research**: Agents use real-time web search for current data
- **Self-Critique**: Agents validate findings (max 2 iterations) before finalizing
- **Comprehensive Reports**: Generates detailed markdown reports with visualizations
- **Modular Design**: Run individual agents or full orchestrated process
- **Completion Notifications**: Optional beep/notification when tasks complete
- **Claude Sonnet 4.5**: All agents powered by the latest Claude model

## Quick Start

### Run Full Research Process

```bash
/gen-ai-research AI-powered contract analysis for German law firms
```

This launches the complete research team with hybrid execution:
- **Phase 1** (Parallel): Market Research + Competitor Analysis + Target Audience
- **Phase 2** (Sequential): Product Strategy → Market Potential
- **Phase 3** (Parallel): Marketing Strategy + Economic Model
- **Phase 4** (Final): Research Coordinator synthesis

### Run Individual Agents

```bash
# Market research only
/research-market AI contract analysis tools

# Competitor analysis only
/analyze-competitors legal tech AI solutions Germany

# Target audience analysis
/define-target-audience legal AI products for law firms

# Product strategy
/strategize-product AI contract analyzer

# Market potential quantification
/assess-market-potential legal AI market DACH

# Marketing strategy
/create-marketing-strategy legal AI product launch

# Economic modeling
/model-economics legal AI SaaS pricing
```

## Deliverables

The research team produces a comprehensive markdown report including:

### Executive Summary
- High-level overview of opportunity
- Key findings across all research areas
- Clear GO/NO-GO/CONDITIONAL recommendation

### Detailed Sections
1. **Market Analysis** - Landscape, size, growth, trends, DACH factors
2. **Competitive Landscape** - Major players, positioning, gaps, threats
3. **Target Audience** - Personas, segments, buying criteria, journey
4. **Product Strategy** - Vision, positioning, features, differentiation
5. **Market Potential** - TAM/SAM/SOM, growth projections, scenarios
6. **Marketing Strategy** - GTM approach, channels, budget, tactics
7. **Economic Model** - Business model, pricing, unit economics, projections
8. **Strategic Roadmap** - 12-month implementation plan
9. **Critical Success Factors** - Must-have elements and metrics
10. **Risks & Mitigation** - Market, competitive, execution, regulatory risks
11. **Action Items** - Immediate, short-term, medium-term next steps

### Visualizations
- Market sizing diagrams (TAM/SAM/SOM)
- Competitive positioning maps
- Customer journey flows
- Revenue projections
- Pricing tier comparisons
- Roadmap timelines

## Directory Structure

```
.claude/
├── agents/                           # Agent prompt templates
│   ├── market-researcher.md
│   ├── competitor-analyst.md
│   ├── target-audience-analyst.md
│   ├── product-strategist.md
│   ├── market-potential-analyst.md
│   ├── marketing-strategist.md
│   ├── economic-modeler.md
│   └── research-coordinator.md
├── commands/                         # Slash commands
│   ├── gen-ai-research.md           # Full orchestration
│   ├── research-market.md           # Individual agents
│   ├── analyze-competitors.md
│   ├── define-target-audience.md
│   ├── strategize-product.md
│   ├── assess-market-potential.md
│   ├── create-marketing-strategy.md
│   └── model-economics.md
└── hooks-setup-instructions.md       # Notification setup guide
```

## Agent Details

### Market Researcher
**Expertise**: Market analysis, trend identification, opportunity assessment
**Outputs**: Market landscape, size/growth data, pain points, technology trends, DACH-specific factors
**Research Methods**: Web search for market reports, industry news, adoption statistics

### Competitor Analyst
**Expertise**: Competitive intelligence, market positioning
**Outputs**: Competitor profiles, competitive matrix, market gaps, differentiation opportunities
**Research Methods**: Web search for competitors, product reviews, pricing, DACH presence

### Target Audience Analyst
**Expertise**: Customer segmentation, persona development, buyer behavior
**Outputs**: Customer personas, segmentation, buying criteria, customer journey, beachhead market recommendation
**Research Methods**: Web search for case studies, buyer behavior patterns, DACH preferences

### Product Strategist
**Expertise**: Product vision, positioning, feature strategy
**Outputs**: Product concept, value proposition, positioning, feature roadmap, competitive advantages
**Dependencies**: Requires market, competitive, and audience research

### Market Potential Analyst
**Expertise**: Market sizing, quantitative analysis, financial modeling
**Outputs**: TAM/SAM/SOM calculations, growth projections, revenue scenarios, customer acquisition potential
**Research Methods**: Web search for market size data, growth rates, benchmarks

### Marketing Strategist
**Expertise**: Go-to-market strategy, customer acquisition, demand generation
**Outputs**: GTM plan, channel strategy, messaging framework, marketing tactics, budget allocation
**Dependencies**: Requires product strategy, audience, and market potential analysis

### Economic Modeler
**Expertise**: Pricing strategy, unit economics, financial projections
**Outputs**: Business model, pricing tiers, LTV/CAC analysis, financial projections, economic moats
**Research Methods**: Web search for competitor pricing, SaaS benchmarks, DACH market data

### Research Coordinator
**Expertise**: Synthesis, strategic thinking, report creation
**Outputs**: Comprehensive integrated report with recommendations and action items
**Process**: Reviews all findings, facilitates critique, resolves conflicts, synthesizes insights

## Workflow & Execution

### Phase 1: Discovery (Parallel)
Three agents run simultaneously to gather foundational research:
- Market Researcher explores the market landscape
- Competitor Analyst maps competitive terrain
- Target Audience Analyst identifies customer segments

**Duration**: ~5-10 minutes per agent
**Parallelization**: All three run concurrently for efficiency

### Phase 2: Strategy (Sequential)
Two agents build on Phase 1 findings:
- Product Strategist synthesizes insights into product strategy
- Market Potential Analyst quantifies the opportunity

**Duration**: ~5-7 minutes per agent
**Dependencies**: Each requires Phase 1 outputs

### Phase 3: Tactical Planning (Parallel)
Two agents develop implementation plans:
- Marketing Strategist creates GTM strategy
- Economic Modeler builds financial projections

**Duration**: ~5-10 minutes per agent
**Parallelization**: Both run concurrently
**Dependencies**: Require Phases 1 & 2 outputs

### Phase 4: Synthesis (Final)
Research Coordinator produces final report:
- Reviews all agent findings
- Facilitates inter-agent critique (2 iterations max)
- Resolves conflicts and documents consensus
- Creates comprehensive markdown report

**Duration**: ~5-10 minutes
**Dependencies**: Requires all prior phases

### Total Process Time
**Estimated Duration**: 25-40 minutes for complete research process
**Output Size**: 5,000-10,000 word comprehensive report

## Self-Critique & Consensus

Each agent performs self-critique (maximum 2 iterations):
1. **Initial Analysis** - Completes primary research and analysis
2. **First Critique** - Reviews own findings, identifies gaps, refines
3. **Second Critique** - Final validation and refinement (if needed)

The Research Coordinator facilitates cross-agent critique:
- Validates consistency across findings
- Resolves conflicts between agents
- Ensures recommendations are feasible
- Documents any remaining disagreements or uncertainties

## DACH Market Focus

All research is specifically tailored for German-speaking markets:

### Geographic Coverage
- **Germany** (Primary focus - largest market)
- **Austria** (Secondary market)
- **Switzerland** (Premium market, CHF considerations)

### Regional Considerations
- German language quality requirements
- GDPR and EU AI Act compliance
- Data sovereignty concerns
- German business culture (formal, quality-focused)
- Mittelstand (mid-sized companies) importance
- Payment preferences (SEPA, invoice/PO)
- VAT differences (Germany 19%, Austria 20%, Switzerland 8.1%)
- German tech media and platforms (XING vs LinkedIn)
- Local events and conferences

## Competitive Economic Moats

The Economic Modeler specifically addresses how to shield the product against competitors:

### Pricing Moats
- Value-based pricing that captures customer surplus
- Lock-in through annual contracts
- Volume commitments and enterprise agreements

### Product Moats
- Network effects (if applicable)
- Data advantages (proprietary training data)
- Switching costs (integration depth, workflow embedding)
- Technology barriers (AI/ML sophistication)

### Market Moats
- First-mover advantages in specific segments
- Strategic partnerships and integrations
- Brand and reputation in DACH market
- Regulatory compliance certification (EU AI Act, GDPR)

### Scale Moats
- Cost advantages at scale
- Customer acquisition efficiency improvements
- AI model performance with more data

## Setup & Configuration

### Prerequisites
- Claude Code installed and configured
- Internet connection (for web search)
- ~30-60 minutes for full research process

### Installation
The system is already installed if you see this file! All agent templates and slash commands are in the `.claude/` directory.

### Notification Setup (Optional)
See `.claude/hooks-setup-instructions.md` for detailed instructions on setting up beep/sound notifications when tasks complete.

Quick setup for beep on task completion:

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "if [ \"$TOOL_NAME\" = \"Task\" ]; then printf '\\a'; fi",
      "description": "Beep when agent tasks complete"
    }
  }
}
```

Add this to your Claude Code settings file.

## Example Use Cases

### 1. New Product Idea Validation
```bash
/gen-ai-research AI-powered legal contract review for German SMBs
```
**Outcome**: Comprehensive assessment of market opportunity, competition, target customers, and go-to-market strategy.

### 2. Market Entry Planning
```bash
/gen-ai-research Healthcare AI diagnostic assistant for German hospitals
```
**Outcome**: Detailed analysis of German healthcare AI market, regulatory considerations, competitive landscape, and launch strategy.

### 3. Competitive Positioning
```bash
/analyze-competitors Customer service AI chatbots Germany
/strategize-product AI customer service differentiation strategy
```
**Outcome**: Deep competitive analysis followed by differentiated product positioning.

### 4. Market Sizing Exercise
```bash
/research-market Gen AI for accounting automation DACH
/assess-market-potential Accounting AI market size Germany
```
**Outcome**: Market research plus quantified TAM/SAM/SOM and revenue projections.

### 5. Pricing Strategy Development
```bash
/model-economics AI sales assistant SaaS pricing DACH
```
**Outcome**: Pricing tiers, unit economics, financial projections, and competitive pricing analysis.

## Best Practices

### Input Quality
- **Be Specific**: "AI contract analysis for corporate law firms" vs. "legal AI"
- **Include Context**: "B2B SaaS for German Mittelstand" vs. just "SaaS"
- **State Constraints**: "Under €100/month price point" if relevant

### Choosing Full vs. Individual Agents
- **Use Full Process** (`/gen-ai-research`) for:
  - New product ideas
  - Comprehensive market entry decisions
  - Investment/funding decisions
  - Strategic planning initiatives

- **Use Individual Agents** for:
  - Specific questions (pricing, competitors, etc.)
  - Iterative refinement of existing research
  - Quick validation of assumptions
  - Focused deep-dives on specific topics

### Interpreting Results
- **Pay attention to consensus sections** - Areas where all agents agree
- **Note open questions** - These require further validation
- **Review assumptions** - Validate key assumptions with real customers
- **Consider scenarios** - Use the range (conservative/moderate/optimistic)
- **Act on immediate items** - Start with quick-win action items

### Iterating on Research
If initial research needs refinement:
1. Review the report's "Open Questions" section
2. Run specific agents again with refined inputs
3. Use findings to validate/update business plan
4. Test assumptions with real customer conversations

## Limitations & Caveats

### Data Accuracy
- Web search provides current data but may be incomplete
- Market sizing is estimated based on available data
- Competitive information may be partial (private companies)
- Always validate critical numbers with primary research

### DACH Market Specificity
- Focus is German-speaking countries; may miss broader EU trends
- Data availability may be better for Germany than Austria/Switzerland
- Some markets have better data coverage than others

### Agent Capabilities
- Agents synthesize information but don't replace human judgment
- Financial models are projections, not guarantees
- Regulatory advice is general; consult legal counsel for compliance
- Each agent iteration has ~2-minute AI processing overhead

### Critique Limitations
- Maximum 2 critique iterations to balance quality vs. time
- Some disagreements may remain unresolved (documented in report)
- Agents cannot access proprietary company data
- No access to paid market research databases

## Troubleshooting

### Issue: "Agent not found" error
**Solution**: Ensure all files in `.claude/agents/` and `.claude/commands/` are present. Check file permissions.

### Issue: Web search not working
**Solution**: Check internet connection. Ensure Claude Code has web search enabled in settings.

### Issue: Process taking too long
**Solution**: Normal duration is 25-40 minutes. If stuck, check Claude Code logs. Cancel and restart if needed.

### Issue: Incomplete report
**Solution**: Check that all phases completed. Re-run any failed agents individually, then run coordinator again.

### Issue: No beep notification
**Solution**: See `.claude/hooks-setup-instructions.md` for detailed troubleshooting.

### Issue: Conflicting agent findings
**Solution**: This is normal. Check the "Open Questions & Consensus" section in the final report for how conflicts were resolved or documented.

## Advanced Usage

### Custom Agent Modifications
You can modify agent prompts in `.claude/agents/` to:
- Add industry-specific analysis requirements
- Include additional research methodologies
- Adjust output format preferences
- Add custom market factors

### Creating Derivative Commands
Copy and modify slash commands to create specialized variants:
```bash
cp .claude/commands/gen-ai-research.md .claude/commands/healthcare-ai-research.md
```
Then customize the new command for healthcare-specific research.

### Chaining with Other Workflows
Research outputs can feed into:
- Product development planning
- Business plan creation
- Investor pitch deck development
- Strategic OKR setting

### Export and Sharing
Generated reports are standard markdown files that can be:
- Committed to git repositories
- Converted to PDF (using pandoc or similar)
- Imported into Notion, Confluence, etc.
- Shared with stakeholders

## FAQ

**Q: How long does the full research process take?**
A: Typically 25-40 minutes for the complete orchestrated process with all 7 agents plus synthesis.

**Q: Can I run this for non-DACH markets?**
A: The agents are optimized for DACH, but you can modify the agent prompts in `.claude/agents/` to target other regions.

**Q: What if I don't have a specific product idea yet?**
A: Start with an industry or domain (e.g., "Gen AI for manufacturing") and the team will help identify product opportunities.

**Q: How accurate are the market size numbers?**
A: Market sizing is based on available web data and analogous markets. Always validate critical numbers with primary research or professional market reports.

**Q: Can I use this for B2C products?**
A: Yes, though the agents are optimized for B2B SaaS. The analysis will adapt to B2C if that's your focus.

**Q: Do I need to run agents in a specific order?**
A: The `/gen-ai-research` command handles ordering automatically. If running individual agents, follow the dependency flow: Discovery → Strategy → Tactics → Synthesis.

**Q: What happens if an agent finds no data?**
A: Agents will use analogous markets, industry benchmarks, and clearly state assumptions. This is documented in the report's limitations section.

**Q: Can I re-run individual agents to refine findings?**
A: Yes! Run individual agent commands with refined inputs based on initial findings.

**Q: How do I know if the product opportunity is good?**
A: Review the final report's executive summary, which includes a clear GO/NO-GO/CONDITIONAL recommendation with rationale.

**Q: What's the difference between Claude Sonnet 4.5 and earlier versions?**
A: Sonnet 4.5 provides improved reasoning, better web search integration, and more sophisticated analysis. All agents use this latest model.

## Contributing & Customization

### Adding New Agents
1. Create agent prompt in `.claude/agents/your-agent.md`
2. Create slash command in `.claude/commands/your-command.md`
3. Update orchestration in `/gen-ai-research` command
4. Update this README

### Modifying Agent Behavior
Edit the relevant agent prompt file in `.claude/agents/`. All changes take effect immediately.

### Sharing Custom Agents
Export your `.claude/` directory and share with team members. They can drop it into their project directory.

## Support & Resources

- **Claude Code Documentation**: https://docs.claude.com/claude-code
- **Issue Reporting**: Document issues or feature requests in your project documentation
- **Agent Prompts**: All agent logic is in `.claude/agents/` - fully transparent and modifiable

## Version History

### v1.0 (Current)
- Initial release
- 8 specialized agents (7 experts + coordinator)
- Hybrid parallel/sequential execution
- DACH market focus
- Claude Sonnet 4.5 powered
- Web search enabled
- Self-critique mechanism (2 iterations max)
- Comprehensive markdown reports
- Modular slash commands
- Hook notification support

## License & Usage

This Gen AI Research Team system is provided as-is for use with Claude Code. Modify and adapt as needed for your research requirements.

---

**Ready to start?**

```bash
/gen-ai-research your-product-idea-here
```

Let the expert team analyze your Gen AI opportunity! 🚀
