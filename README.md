# skills

A vendor-agnostic **agent skills library**: 171 skills for marketing, SEO/GEO
(AI-search optimization), copywriting, and frontend design — invocable by any
agent that points at this repository.

## Use it

**With any agent (no install):** clone the repo or open it as your agent's
workspace. Agents read [`AGENTS.md`](./AGENTS.md) (or the `CLAUDE.md` /
`GEMINI.md` pointers) and load skills on demand from `.agents/skills/`.
Each skill is a plain folder with a `SKILL.md` entrypoint — no build, no
server, no symlinks.

**With the [skills CLI](https://github.com/vercel-labs/skills)** — install any
skill from this repo into your own agent setup:

```bash
npx skills add francevilla/skills                 # pick interactively
npx skills add francevilla/skills@geo-audit       # one skill
npx skills add francevilla/skills --skill '*' -a universal -y   # everything
```

To materialize the CLI-managed skills into agent-native directories
(`.claude/skills`, `.cursor/…`, etc.) after cloning:

```bash
npx skills experimental_install -a universal      # or: -a claude-code, cursor, codex, '*' …
```

## What's inside

| Group | Count | Highlights |
|---|---|---|
| Frontend design | 1 | `design-taste-frontend` — anti-"AI-slop" site builder (taste-skill 2.5.1) |
| Copywriting | 1 | `copywriting` — conversion page copy |
| GEO / AI search | 8 | `geo-audit`, `geo-fix-*`, `geo-monitor`, `seo-analytics`, `bing-ai-analytics` |
| Marketing workflows | 1 | `marketing-skills` — evidence-led GTM→analytics workflows |
| CMO.so suite | 160 | `cmo-*` — SEO, ads, content, social, email, CRO, analytics, WordPress |

Full catalog and per-skill descriptions: [`AGENTS.md`](./AGENTS.md).

## Layout

```
.agents/skills/<name>/   # all 171 skills (universal agentskills convention)
AGENTS.md                # agent entrypoint + full catalog + provenance
CLAUDE.md / GEMINI.md    # redirects for Claude Code / Gemini CLI
skills-lock.json         # version pins for the CLI-installed skills
```

## Updating

- CLI-managed skills: `npx skills update` (uses `skills-lock.json`).
- CMO.so suite: re-run `npx @cmo-so/skills install -g -a opencode`, then copy
  `~/.config/opencode/skills/cmo-*` over `.agents/skills/`.
- `marketing-skills`: re-clone
  [elavenile/marketing-agent-skills](https://github.com/elavenile/marketing-agent-skills)
  and copy `marketing-skills/` over `.agents/skills/marketing-skills`.

## Notes

- Skills run with full agent permissions; review before use (several bundle
  executable scripts).
- Some `cmo-*` skills expect the CMO.so MCP server (`https://mcp.cmo.so/mcp`)
  and account for live data; they degrade gracefully to standalone guidance.
- Each vendored skill keeps its upstream license — see the source repositories
  listed in `AGENTS.md`.
