# Bing AI Performance Export Schema

Use this reference when identifying and normalizing Bing Webmaster Tools `AI Performance` CSV/JSON exports.

## Supported Export Types

| Export type | Expected content |
|-------------|------------------|
| `summary` | Total citations, average cited pages, selected date window, and high-level trend metrics. |
| `citedPages` | URLs cited in AI-generated answers, citation counts, and optional trend columns. |
| `groundingQueries` | Query phrases used by Bing AI retrieval/grounding systems and related citation counts or pages. |
| `trends` | Time-series citation activity by date, week, or other export bucket. |
| `intents` | Bing intent labels and related citation activity. |
| `topics` | Bing topic labels and related citation activity. |
| `citationShare` | Relative citation presence, share, or visibility metrics. |
| `compare` | Comparison targets such as domains, sources, or competitors and their citation metrics. |
| `recommendations` | Bing-provided recommendations, suggestions, issue labels, or opportunity text. |

If an export mixes multiple types, classify it as `mixed` and normalize each row using the fields that are present.

## Field Aliases

Field names may vary across preview exports. Match case-insensitively and normalize whitespace, punctuation, underscores, and hyphens before comparing aliases.

| Normalized field | Common aliases |
|------------------|----------------|
| `date` | `date`, `day`, `week`, `period`, `time`, `time bucket`, `start date`, `end date` |
| `page` | `page`, `url`, `cited url`, `cited page`, `page url`, `referenced url` |
| `groundingQuery` | `grounding query`, `grounding queries`, `query`, `query phrase`, `retrieval query`, `key phrase` |
| `intent` | `intent`, `search intent`, `ai intent`, `intent label` |
| `topic` | `topic`, `topics`, `subject`, `theme`, `topic label` |
| `citations` | `citations`, `total citations`, `citation count`, `cited count`, `ai citations` |
| `averageCitedPages` | `average cited pages`, `avg cited pages`, `average pages cited`, `avg pages cited` |
| `citationShare` | `citation share`, `share`, `visibility share`, `share of citations` |
| `comparisonTarget` | `target`, `domain`, `competitor`, `compared domain`, `source`, `site` |
| `recommendation` | `recommendation`, `suggestion`, `insight`, `opportunity`, `recommended action` |
| `surface` | `surface`, `experience`, `ai experience`, `product`, `integration` |

## Normalized Row

Use this model for comparable evidence:

```json
{
  "source": "bingAiPerformance",
  "exportType": "citedPages",
  "surface": "mixed",
  "date": "2026-06-01",
  "page": "https://example.com/page",
  "groundingQuery": "example query",
  "intent": "research",
  "topic": "example topic",
  "citations": 42,
  "averageCitedPages": "",
  "citationShare": "",
  "comparisonTarget": "",
  "recommendation": "",
  "rawMetricName": "Total Citations"
}
```

Leave unknown values blank. Keep raw rows available for audit notes, but do not include full private exports in public reports.

## Export Type Detection

Use file names and fields together:

- File names containing `grounding`, `query`, or `queries` suggest `groundingQueries`.
- File names containing `page`, `url`, or `cited` suggest `citedPages`.
- File names containing `trend`, `daily`, `weekly`, or `time` suggest `trends`.
- File names containing `intent` suggest `intents`.
- File names containing `topic` suggest `topics`.
- File names containing `share` suggest `citationShare`.
- File names containing `compare`, `comparison`, or `competitor` suggest `compare`.
- File names containing `recommendation`, `suggestion`, `insight`, or `opportunity` suggest `recommendations`.

If detection is uncertain, state the uncertainty and analyze only fields that are clear.

## Interpretation Rules

- Treat preview or sampled data as directional evidence, not complete measurement.
- Do not infer user prompts from grounding queries. Grounding queries are retrieval phrases, not necessarily original user questions.
- Do not compare citation counts to traditional search clicks, CTR, or average position as if they share the same denominator.
- Do not treat `citationShare` or compare exports as market-wide share unless the export clearly defines the comparison set.
- Do not treat cited pages as ranked pages unless the export explicitly provides a ranking field.
