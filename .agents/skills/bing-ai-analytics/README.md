# bing-ai-analytics

Analyze Bing Webmaster Tools `AI Performance` exports for Bing AI citation visibility.

`bing-ai-analytics` is an Agent Skill for first-party Bing AI visibility data. It reads user-provided CSV/JSON exports and produces evidence-backed insights about cited pages, grounding queries, intents, topics, citation share, compare data, and Bing recommendations.

It does not perform logged-in UI scraping, call unofficial APIs, analyze non-Bing AI platforms, or produce a `GEO Score`.

---

## What Gets Analyzed

| Export | Focus |
|--------|-------|
| Summary metrics | Total citations, average cited pages, visibility trend direction |
| Cited pages | Page-level citation activity, concentration risk, declining pages |
| Grounding queries | Query clusters, cited page-query fit, content gaps |
| Intents and topics | Strong areas, weak areas, expansion opportunities |
| Citation share and compare | Relative citation presence and comparison target gaps |
| Bing recommendations | Source recommendations converted into prioritized actions |

## Typical Inputs

- Bing Webmaster Tools `AI Performance` CSV exports
- Bing Webmaster Tools `AI Performance` JSON exports
- Export folders containing cited pages, grounding queries, trends, intents, topics, citation share, compare, or recommendations

## Boundaries

Use `bing-ai-analytics` for private Bing first-party AI Performance exports.

Use `seo-analytics` for traditional SEO data from Google Search Console, Bing Webmaster search stats, and GA4 Organic Search.

Use `geo-audit` for public website GEO readiness audits.

## Report Output

Reports should include:

- Executive Summary
- Data Scope and Limitations
- AI Visibility Summary
- Cited Pages
- Grounding Queries
- Intents and Topics
- Citation Share and Compare
- Bing Recommendations
- Prioritized Bing AI Actions
- Questions to Confirm

Each high-priority action should include the evidence source, affected page/query/topic/intent, recommended action, expected AI visibility impact, confidence, and whether more data is needed.

## Non-Goals

- No logged-in UI scraping
- No unofficial or reverse-engineered APIs
- No live fetch script in the first version
- No ChatGPT, Perplexity, Gemini, Google AI Overviews, or third-party AI visibility data
- No `GEO Score`, ranking score, authority score, or guaranteed placement claims

## Related Skills

| Skill | Relationship |
|-------|--------------|
| [seo-analytics](../seo-analytics/) | Analyzes traditional SEO data from GSC, Bing Webmaster search stats, and GA4 |
| [geo-audit](../geo-audit/) | Audits whether a public site can be understood, cited, and recommended by AI systems |
| [geo-monitor](../geo-monitor/) | Tracks GEO audit score changes over time |
