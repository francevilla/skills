# Bing AI Analytics Report Outline

Use this outline when producing a report from Bing Webmaster Tools `AI Performance` exports.

## 1. Executive Summary

State the main Bing AI visibility opportunities in priority order. Separate citation visibility, page/topic coverage, and measurement limitations.

## 2. Data Scope and Limitations

Include:

- Site/profile when known
- Date window
- Export files and inferred export types
- Filters used
- Missing fields or incomplete exports
- Preview, sampled, or directional-data caveats
- Whether analysis used only supplied exports

## 3. AI Visibility Summary

Analyze when data is available:

- Total citations
- Average cited pages
- Citation trend direction
- Concentration across pages, topics, or intents
- Notable increases or declines

Do not describe these metrics as rankings or authority scores.

## 4. Cited Pages

Analyze:

- Most cited pages
- Pages with declining citation activity
- Pages cited for multiple topics or grounding query clusters
- Pages with citation concentration risk
- Pages that need clearer structure, stronger evidence, or fresher information

## 5. Grounding Queries

Analyze:

- Frequent grounding query phrases
- Query clusters and recurring modifiers
- Query-page fit
- Topics implied by grounding queries but weakly covered on cited pages
- Ambiguous or underspecified query groups that require human confirmation

Do not treat grounding queries as original user prompts unless the export explicitly says so.

## 6. Intents and Topics

Analyze:

- Strongest intent/topic areas
- Weak or missing areas relevant to the site
- Over-concentrated topics
- Opportunities to strengthen coverage or split mixed-intent pages

## 7. Citation Share and Compare

Analyze when data is available:

- Relative citation presence
- Comparison targets that outperform the site
- Pages, topics, or intents where the site has weaker citation share
- Cases where field definitions prevent direct comparison

State the comparison set when known. If unknown, warn that share metrics are directional.

## 8. Bing Recommendations

Use `recommendation-handling.md`:

- Summarize Bing recommendations without long verbatim copying.
- Mark each as supported, partially supported, unsupported, conflicting, or needs confirmation.
- Tie recommendations to cited pages, grounding queries, topics, intents, or trends when possible.

## 9. Prioritized Bing AI Actions

Use this table:

| Priority | Evidence | Affected page/query/topic/intent | Action | Expected AI visibility impact | Confidence | More data needed? |
|----------|----------|----------------------------------|--------|-------------------------------|------------|-------------------|
| High | Cited pages + grounding queries | `/guide` + "example query" | Add direct answer block, evidence, and updated comparison table | Better citation eligibility for related Bing AI answers | Medium | No |

Each high-priority action must be executable and evidence-backed. Avoid generic advice without a page, query, topic, intent, recommendation source, or expected metric impact.

## 10. Questions to Confirm

Ask only questions that change the recommendation:

- Whether a cited page is strategically important
- Which comparison targets are real competitors
- Whether a topic/intent is in scope for the business
- Whether missing pages or exports exist elsewhere
- Whether recommendations conflict with brand, legal, or editorial constraints

## Machine-Readable Summary

When useful, append a compact block:

```yaml
BING_AI_ANALYTICS_META:
  site: https://example.com
  startDate: 2026-06-01
  endDate: 2026-06-30
  sources:
    bingAiPerformance: true
  exportTypes:
    citedPages: true
    groundingQueries: true
    recommendations: true
  language: en
```
