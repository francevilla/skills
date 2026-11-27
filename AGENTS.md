# AGENTS.md — Agent Skills Library

This repository is a **vendor-agnostic skill library**: 171 ready-to-use skills for
marketing, SEO/GEO (AI-search optimization), copywriting, and frontend design.

Any agent working in this repository can invoke any skill. No installation, build
step, or MCP server is required for the skills themselves.

## How to invoke a skill

1. Pick the skill whose description best matches the user's task (see the catalog
   below, or browse `.agents/skills/<name>/SKILL.md` frontmatter).
2. **Read `.agents/skills/<name>/SKILL.md` in full** and follow its instructions.
3. Load extra files (`references/`, `assets/`, `scripts/`) only when the SKILL.md
   tells you to — skills use progressive disclosure; don't preload everything.
4. Skills run with your full agent permissions. Prefer reading over executing;
   run bundled scripts only when the task requires them.

If no skill matches the task, proceed normally — skills are helpers, not gates.

## Layout

```
.agents/skills/<skill-name>/   # one folder per skill (universal agentskills convention)
  SKILL.md                     # entrypoint: name, description, instructions
  references/  assets/  scripts/  evals/   # optional supporting files
skills-lock.json               # pins the 10 CLI-installed skills (source + commit + hash)
```

## Catalog

### Core (installed individually)

| Skill | Use for |
|---|---|
| `design-taste-frontend` | Building/restyling professional websites (landing, SaaS, shop, portfolio) with an anti-"AI-slop" design system; HTML/CSS or React/Next/Vue/Svelte/Astro/Tailwind |
| `copywriting` | Writing/rewriting page copy (homepage, landing, pricing, features); conversion-focused, no AI tells |
| `marketing-skills` | Evidence-led marketing workflows: GTM, competitor research, SEO, content, social, email, video, conversion, analytics |

### GEO / AI-search visibility (from Cognitic-Labs/geoskills)

| Skill | Use for |
|---|---|
| `geo-audit` | Full GEO audit — why AI systems can't discover/cite/recommend a site, with prioritized fixes |
| `geo-compare` | Benchmark AI-visibility scores across 2–3 competing sites |
| `geo-fix-content` | Rewrite content for AI citability (remove hedging, add data support) |
| `geo-fix-schema` | Generate ready-to-use JSON-LD structured data |
| `geo-fix-llmstxt` | Generate `llms.txt` / `llms-full.txt` |
| `geo-monitor` | Re-audit and track GEO score changes vs. a baseline |
| `seo-analytics` | Analyze GSC / Bing / GA4 exports, queries, CTR, rankings |
| `bing-ai-analytics` | Analyze Bing Webmaster Tools AI Performance exports (citations, grounding queries) |

### CMO.so marketing suite (160 skills, `cmo-*` prefix)

- **Strategy & brand:** `cmo-marketing-plan` `cmo-marketing-audit` `cmo-marketing-ideas` `cmo-marketing-psychology` `cmo-positioning` `cmo-market-sizing` `cmo-brand-naming` `cmo-brand-profile` `cmo-brand-protection` `cmo-product-launch` `cmo-proposals` `cmo-public-relations` `cmo-co-marketing` `cmo-expert-panel`
- **SEO & AI visibility:** `cmo-seo-audit` `cmo-seo-plan` `cmo-seo-monitoring` `cmo-seo-opportunities` `cmo-technical-seo` `cmo-page-seo` `cmo-local-seo` `cmo-international-seo` `cmo-ecommerce-seo` `cmo-programmatic-seo` `cmo-keyword-research` `cmo-keyword-clustering` `cmo-search-intent` `cmo-site-architecture` `cmo-link-building` `cmo-schema-markup` `cmo-entity-audit` `cmo-ai-visibility` `cmo-ai-visibility-audit` `cmo-ai-brand-monitoring` `cmo-ai-citation-gaps` `cmo-ai-prompt-research` `cmo-aeo-content` `cmo-agent-readiness` `cmo-directory-submissions` `cmo-free-tools`
- **Content:** `cmo-content-strategy` `cmo-content-brief` `cmo-content-refresh` `cmo-content-repurposing` `cmo-blog-planner` `cmo-blog-writing` `cmo-copywriting` `cmo-copy-editing` `cmo-humanize` `cmo-draft-review` `cmo-newsletter` `cmo-lead-magnets` `cmo-thought-leadership`
- **Paid ads:** `cmo-ads-strategy` `cmo-ads-audit` `cmo-ads-budget` `cmo-ads-launch` `cmo-ads-monitoring` `cmo-ads-competitor-research` `cmo-ad-creative` `cmo-ad-video` `cmo-google-ads` `cmo-meta-ads` `cmo-linkedin-ads` `cmo-wasted-spend`
- **Social & video:** `cmo-social-strategy` `cmo-social-distribution` `cmo-social-listening` `cmo-social-analytics` `cmo-social-crisis` `cmo-organic-social` `cmo-community` `cmo-reddit` `cmo-pinterest` `cmo-instagram` `cmo-instagram-posts` `cmo-facebook` `cmo-facebook-posts` `cmo-tiktok` `cmo-tiktok-posts` `cmo-x-growth` `cmo-linkedin` `cmo-linkedin-strategy` `cmo-linkedin-posts` `cmo-linkedin-profile` `cmo-linkedin-engagement` `cmo-employee-advocacy` `cmo-influencer` `cmo-short-form-video` `cmo-video-production` `cmo-video-repurposing` `cmo-youtube` `cmo-youtube-strategy` `cmo-youtube-posts` `cmo-google-business` `cmo-google-business-posts` `cmo-china-social` `cmo-open-social`
- **Email & lifecycle:** `cmo-cold-email` `cmo-email-sequences` `cmo-email-deliverability` `cmo-sms-whatsapp` `cmo-onboarding-activation` `cmo-signup-flow` `cmo-churn-prevention` `cmo-referral-program` `cmo-paywalls`
- **CRO & web:** `cmo-landing-page-audit` `cmo-landing-page-builder` `cmo-page-cro` `cmo-form-cro` `cmo-checkout-cro` `cmo-popups` `cmo-ab-testing` `cmo-website-setup` `cmo-app-store-optimization`
- **Analytics & ops:** `cmo-tracking-setup` `cmo-attribution` `cmo-campaign-analytics` `cmo-closed-loop-measurement` `cmo-weekly-report` `cmo-daily` `cmo-routines` `cmo-marketing-automation` `cmo-ops-autopilot` `cmo-autopilot` `cmo-revops` `cmo-client-report` `cmo-connect` `cmo-memory` `cmo-team-access`
- **Sales & research:** `cmo-prospecting` `cmo-sales-enablement` `cmo-sales-signals` `cmo-customer-research` `cmo-competitor-research` `cmo-competitor-pages` `cmo-events-webinars`
- **WordPress:** `cmo-wp-booking` `cmo-wp-builder` `cmo-wp-child-theme` `cmo-wp-clone` `cmo-wp-faq` `cmo-wp-images` `cmo-wp-languages` `cmo-wp-migrate` `cmo-wp-motion` `cmo-wp-move` `cmo-wp-operation` `cmo-wp-page-design` `cmo-wp-qa` `cmo-wp-sections` `cmo-wp-security` `cmo-wp-seo` `cmo-wp-seo-technical` `cmo-wp-shop` `cmo-wp-vibe-coding`

> Note: some `cmo-*` skills expect the CMO.so MCP server (`https://mcp.cmo.so/mcp`)
> and a CMO.so account for live data. They still provide standalone guidance
> without it. See each SKILL.md for details.

## Provenance

| Source | Version/commit | Skills |
|---|---|---|
| [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | `952435f6` | `design-taste-frontend` |
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | `2bf95edb` | `copywriting` |
| [Cognitic-Labs/geoskills](https://github.com/Cognitic-Labs/geoskills) | `a564148c` | 8 geo/seo skills |
| [AI-Marketing-OS-LTD/cmo-so-skills](https://github.com/AI-Marketing-OS-LTD/cmo-so-skills) (npm `@cmo-so/skills`) | `0.28.10` | 160 `cmo-*` skills |
| [elavenile/marketing-agent-skills](https://github.com/elavenile/marketing-agent-skills) | `b7d145d3` | `marketing-skills` |

Each skill is vendored as plain files (no symlinks, no submodules). Upstream
licenses apply; review a skill before running its bundled scripts.
