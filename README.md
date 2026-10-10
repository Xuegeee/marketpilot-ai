# MarketPilot AI

A reusable Codex skill for evidence-led market-entry discovery and polished Word reporting.

MarketPilot AI was designed by **Xuegeee** as an AI workflow and strategy-research portfolio project. It turns an open-ended expansion question into confirmed client inputs, verified public-source research, an explicit feasibility assessment, and a decision-ready report.

## What makes the workflow different

- **Confirmation before research:** Step 0 confirms the brand, offer, origin, target geography, budget, timing, constraints, output format, and report language before broad research begins.
- **Cross-industry and cross-market:** The same decision framework works for restaurants, apparel, consumer technology, mobility, and other categories entering a country, region, or city.
- **Evidence discipline:** Decision-critical claims must be supported by current, visible sources that match the stated geography and time period. Unverified claims remain outside the score and recommendation.
- **Explicit Discovery-stage scoring:** Five dimensions use anchored scoring. Missing evidence is recorded as `Unknown` or `Not Scorable`, rather than converted into an average score.
- **Policy-aware feasibility:** Verified subsidies, tax benefits, infrastructure support, and other favorable policies can add a separately disclosed bonus.
- **Decision-oriented strategy:** The report covers market sizing, customer segments, primary audience selection, competitive positioning, the status-quo alternative, pricing, entry modes, budget, action plan, and validation gates.
- **Consistent multilingual output:** The selected report language applies to headings, tables, charts, source labels, and navigation—not only body paragraphs.
- **Word quality control:** Reports use one visual system, start each major section on a new page, include a table of contents, and are rendered page by page before delivery.

## Workflow

1. **Step 0 — confirm the brief.** Conduct only limited company verification before the client confirms the inputs.
2. **Build the evidence base.** Research demand, consumers, competition, regulation, economics, entry modes, partners, and favorable policies.
3. **Size and segment the opportunity.** Develop TAM, SAM, SOM, a demand-side model, geographic priorities, and multiple customer segments.
4. **Assess feasibility.** Score only supported dimensions, state evidence confidence, isolate unknowns, and disclose any policy bonus separately.
5. **Recommend and sequence.** Set the entry thesis, pricing logic, partner approach where relevant, budget, milestones, validation gates, and stop conditions.
6. **Generate and verify the report.** Apply the invariant report schema, add linked sources, render the Word document, and inspect every page.

## Repository structure

```text
marketpilot-ai/
├── README.md
└── skill/
    └── marketpilot-ai/
        ├── SKILL.md
        ├── agents/openai.yaml
        ├── assets/market-entry-report-master.docx
        └── references/
            ├── feasibility-scoring.md
            └── report-schema.md
```

## Install in Codex

Copy the skill directory into your Codex skills folder:

```bash
cp -R skill/marketpilot-ai ~/.codex/skills/marketpilot-ai
```

The skill supports automatic invocation through natural-language market-entry requests in multiple languages. A fixed command is not required.

## Design principles

- Public evidence supports Discovery-stage decisions; it does not replace paid data, field research, legal review, or professional advice.
- Market size and feasibility are not the same question.
- A missing fact is not a neutral fact.
- A recommendation should identify what to validate next, what would change the decision, and when to stop.
- Report consistency is part of analytical quality, not a cosmetic afterthought.

## Author and usage

Created by **Xuegeee**. This repository is shared as a portfolio artifact. No license is granted unless explicitly stated.
