# Recommendation Handling

Use this reference when a Bing `AI Performance` export includes recommendations, suggestions, insights, or opportunity text.

## Core Rule

Treat Bing-provided recommendations as evidence, not final instructions. Preserve the source signal, deduplicate related items, and convert them into prioritized actions that fit the page, query, topic, and intent evidence.

## Recommendation Status

| Status | Use when |
|--------|----------|
| `supported` | Bing recommendation aligns with export evidence such as cited page, grounding query, topic, or trend data. |
| `partially supported` | The recommendation is plausible but export evidence is incomplete. |
| `unsupported` | The recommendation has no clear backing in the supplied exports. |
| `conflicting` | The recommendation conflicts with stronger evidence or user constraints. |
| `needs confirmation` | The recommendation depends on business goals, page ownership, or data not present in exports. |

## Action Categories

| Category | Typical action |
|----------|----------------|
| `content clarity` | Clarify headings, definitions, answer blocks, tables, or summaries for cited topics. |
| `content depth` | Add missing subtopics, evidence, examples, comparisons, or freshness updates. |
| `entity consistency` | Align brand, product, author, location, or service names across page sections. |
| `query-page fit` | Improve the match between grounding queries and cited page content. |
| `topic expansion` | Build or strengthen pages for weak but relevant topics/intents. |
| `technical discoverability` | Check indexability, canonicalization, robots controls, structured data, or freshness signals. |
| `measurement follow-up` | Request more exports, a longer date window, or missing compare/citation-share data. |

## Priority Rules

Assign priority by combining impact, evidence strength, and execution clarity:

- `High`: strong evidence, important page/topic/query, clear action, likely AI visibility impact.
- `Medium`: useful evidence but lower impact, weaker confidence, or more implementation ambiguity.
- `Low`: exploratory, missing evidence, or mostly hygiene.

Never mark an action `High` without a concrete affected page, grounding query, topic, intent, or recommendation source.

## Required Action Fields

Use this action table:

| Priority | Evidence | Affected page/query/topic/intent | Action | Expected AI visibility impact | Confidence | More data needed? |
|----------|----------|----------------------------------|--------|-------------------------------|------------|-------------------|
| High | Bing recommendation + cited page export | `/docs/example` + topic | Add concise answer block and supporting evidence | Better citation eligibility for related grounding queries | Medium | No |

## Guardrails

- Do not copy long recommendation text verbatim into a public report. Summarize it and cite the export row or file path.
- Do not invent a recommendation when only summary metrics are available.
- Do not recommend manipulative content patterns, hidden text, keyword stuffing, or misleading entity claims.
- Do not claim an action will guarantee citations or placement in AI answers.
- If recommendations conflict with user constraints, list the conflict and ask for confirmation.
