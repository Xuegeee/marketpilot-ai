---
name: marketpilot-ai
description: Evaluate a company, brand, product, or service entering any new country or city through a structured market-entry workflow and polished Word report. Use for natural-language requests about market entry, entering or launching in a market, international expansion, “进入某个市场”, “进驻某国或城市”, and rerunning or updating prior cases; explicit $marketpilot-ai invocation is not required.
---

# MarketPilot AI

Use a confirmation-first workflow and one invariant report schema. Change the evidence and analysis by industry; do not redesign the workflow or document for each case. Treat every assessment as a Discovery-stage market-entry decision: determine whether the opportunity merits validation and what must be learned next, rather than grading the company as though it were already launch-ready.

## Invocation

- Allow implicit invocation. The user does not need to type `$marketpilot-ai` or use a fixed command.
- Trigger when the user asks to assess, plan, compare, rerun, or update entry into a new country, region, or city, including natural-language phrases such as `market entry`, `enter the [market] market`, `launch in [country]`, `expand into [country]`, `进入某个市场`, `进驻某国`, or `进入某城市`.
- Apply the same workflow to every target market. Do not assume the target is China unless the user specifies China.
- Do not trigger for general market research that has no market-entry, geographic-expansion, or launch decision.

## Required workflow

0. Reply in the language used by the user's latest substantive message. If the user changes language, follow the new language unless they explicitly request otherwise. Treat the confirmed report language as a deliverable-wide requirement, not merely the language of the body paragraphs.
1. Run Step 0 before broad research.
2. For a public company, search only enough current official information to identify the company, products, origin market, and origin-market consumer/pricing context. Do not form a market-entry judgment yet.
3. Ask the client to confirm company/brand, product, origin, target geography, budget, timing, constraints, whether a Word report is required, and the preferred report language. Ask the report-language question explicitly before generating any report unless the client has already explicitly specified it for the current case. Do not infer the report language from the conversation language, and do not ask for target-market consumer or pricing assumptions.
4. If the company voluntarily provides performance in other markets, use it; do not request it separately.
5. After confirmation, research the full market, competition, consumers, regulation, economics, entry modes, partners, favorable policy conditions, and evidence gaps.
6. Apply the Live-Source Verification Gate: treat search snippets, cached text, summaries, and crawler extracts as clues only. Verify decision-critical facts on current visible primary pages. The cited page must explicitly support both the claim and the stated geography. For shipping, delivery, store availability, licensing, or market-presence claims, require the current page to name the relevant country or city; never infer a specific market from generic wording such as `international shipping` or `global availability`. Mark unresolved conflicts `Unverified`; exclude them from executive decisions, scores, and recommendations.
7. Draft the report using the exact schema in [report-schema.md](references/report-schema.md).
8. Run the Language and Citation Quality Gate below before layout work. Do not proceed with a mixed-language, literal-sounding, or unlinked-source draft.
9. For Word output, use the documents skill and treat [market-entry-report-master.docx](assets/market-entry-report-master.docx) as the visual authority. Preserve its page geometry, cover, headers, footers, typography, heading ladder, table styling, callouts, spacing, and source formatting. Render every page and inspect it before delivery.

## Content rules

- Use the fixed disclaimer meaning in the schema and render it in the confirmed report language.
- Merge Executive Decision Page and Executive Summary.
- Define Reason to Believe as why the consumer believes the brand promise.
- Put origin-market consumer profile and origin-market pricing context inside the `Confirmed Inputs` table. Never create a separate origin-market profile section outside that table.
- Put target-market consumer analysis only in `Target Audience` after research.
- In `Target Audience`, identify multiple distinct, evidence-supported customer segments before choosing a primary segment. Compare their need or occasion, attractiveness, accessibility, brand fit, economics, and competitive intensity; then name one primary segment and explain why it outranks the alternatives, including the principal trade-off. Do not present a single segment as primary without showing the alternatives considered.
- Derive pricing recommendations after and from the competitive landscape and landed economics.
- Include competitor type, target customer, positioning, competitive advantage, and threat/implication.
- Include the status quo / “do nothing” alternative and competitive white space.
- Cover market definition, TAM/SAM/SOM, demand-side model, geographic opportunity, category growth/maturity, and evidence gaps. Keep the TAM/SAM/SOM analytical structure, but localize the section title, table headers, and layer names into the confirmed report language. Use the full layer names rather than acronym-only cells. For example, a Chinese report should use `总可寻址市场`、`可服务市场`、`可获得市场`, with `TAM / SAM / SOM` shown once in the section title or first explanation if useful; an English report should use `Total Addressable Market`, `Serviceable Available Market`, and `Serviceable Obtainable Market`. Do not use a store-capacity model as market size.
- Include entry-mode comparison in the action plan.
- Include partner strategy only when relevant; if included, place it in Recommendations.
- Score feasibility as a Discovery-stage opportunity using the explicit anchors, Unknown treatment, evidence-status rules, and favorable-policy adjustment in [feasibility-scoring.md](references/feasibility-scoring.md). Never convert missing evidence into a neutral or average score. Calculate the base composite and any policy bonus separately at full precision, then round only the final adjusted score to the nearest 0.5 point. At exact quarter-point ties, round upward. Display one decimal place; never publish a more granular final score.
- Group sources by original-source language and target-market relevance. Localize every group heading into the confirmed report language (for example, use `英文信源` and `中文信源` in a Chinese report rather than English headings). If the target market's primary research language is English, one English-language source group is sufficient. Annotate what each source supports and disclose conflicting estimates and evidence gaps. Every source entry must include a working clickable hyperlink to the exact original page, not a search-results page, bare home page, or uncited publication name.
- Keep Step 0 concise. Collect evidence before judging; do not front-load research conclusions.

## Language and citation quality gate

Before layout or delivery, fail the draft unless all conditions below are satisfied:

- Every user-facing element is in the confirmed report language: cover text, disclaimer, section and subsection titles, table headers and cells, chart titles, axes, legends, data labels, figure captions, callouts, annotations, footnotes, source-group headings, and navigation text.
- Proper nouns, registered brand names, official product or model names, and widely used acronyms may remain in their official form. Surrounding explanations must be localized, and an unfamiliar acronym or local-market mechanism must be explained in plain language on first use.
- The prose has passed a native-quality terminology and fluency review. Reject literal translations, awkward calques, unexplained local jargon, and inconsistent terminology. When a foreign-market mechanism has no natural direct equivalent, explain how it works in the report language and optionally give the original term in parentheses. For example, describe the UK mechanism commonly called `salary sacrifice` as an employer-provided electric-vehicle leasing plan paid through pre-tax salary deductions, rather than translating the words literally.
- Every source has a localized title or description, a concise annotation of what it supports, and a visible link label in the report language (for example, `查看原文` in Chinese) connected to the exact original source URL.
- Each citation has passed a claim-to-source check: the linked page states the attributed fact, applies to the stated geography and time period, and does not merely discuss a related but different claim.
- All external links have been structurally checked in the generated Word file and, when access permits, opened or otherwise validated as resolving to the intended source. A source without a usable link must be labeled as such and cannot support a decision-critical claim unless the limitation is explicitly disclosed.
- A final search for residual interface or template language has been completed. Any language that differs from the confirmed report language must be intentional and limited to the allowed official-name or acronym exceptions above.

## Consistency gate

Before delivery, compare the new report against `market-entry-report-master.docx` and fail the draft if any of these drift without an explicit client request:

- section order or nesting;
- location of Confirmed Inputs fields;
- cover composition;
- page size or margins;
- typefaces, type sizes, colors, or heading spacing;
- header/footer alignment or page-number treatment;
- bullet indentation or line spacing;
- table geometry, cell padding, fills, or header treatment;
- callout and red-flag styling;
- source-list structure.

Also fail the draft if requested-language coverage, terminology fluency, or source hyperlinks violate the Language and Citation Quality Gate.

Content length may change pagination, but it must not change the style system.

### Canonical pagination and component forms

- Reserve page 2 for a localized, one-page table of contents listing the Executive Summary & Decision, Sections 1–12, and Sources & Evidence Base with accurate page numbers. Keep it to top-level entries unless the client requests more detail.
- Start every top-level report section on a new page: `Executive Summary & Decision`, Sections 1–12, and `Sources & Evidence Base`. Do not place two level-one sections on the same page. Subsections may continue naturally unless readability requires a page break.
- Drive typography through named roles, not one-off formatting. Every paragraph at the same hierarchy level must use the same font family, size, weight, color, spacing, and page-break behavior. Before delivery, audit Heading 1, Heading 2, Heading 3, body, bullets, source entries, table headers, and table bodies for direct-formatting drift.
- Render `Quick Blocker Scan` in one invariant conclusion-based form: a concise overall blocker conclusion followed by separate evidence or action bullets. Do not use a blocker table, scorecard, or case-specific visual form.
- Render `SWOT & Red Flags` in one invariant form. Use the four labeled groups `Strengths`, `Weaknesses`, `Opportunities`, and `Threats` (localized), with every factor on its own bullet or line. Never compress multiple factors into one semicolon-separated paragraph. Follow with a separately labeled `Red Flags` list.
- Keep top-level section titles fixed to the report schema. Put case-specific time periods, budget totals, market names, and other dynamic detail in the section body or a level-two heading, not in the level-one title.
- Do not add an extra top-level appendix or case-specific section for material that belongs in Sections 1–12. For example, put a first-city rationale under Recommendations or Geographic Opportunity, and put its citations in Sources.
