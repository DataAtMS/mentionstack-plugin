# Mentionstack Plugin

Internal Claude Code plugin powering Mentionstack agency delivery — GEO/AEO/SEO content production, research, and analysis.

## Skills

All skills are namespaced as `/mentionstack:<skill-name>`.

### Foundation (SEO)

| Skill | What it does |
|-------|-------------|
| [`seo/content-writer`](seo/content-writer/) | DataForSEO-driven blog content with Mentionstack humanization rules + scientific delivery standard (hypothesis, keywords, target LLMs, expected outcome, approval gate). |
| [`seo/seo-analysis`](seo/seo-analysis/) | Full SEO audit with quick wins, technical issues, and 30-day plan. |
| [`seo/keyword-research`](seo/keyword-research/) | Keyword discovery, intent classification, topic clusters, content calendar. |
| [`seo/meta-tags-optimizer`](seo/meta-tags-optimizer/) | Title tags, meta descriptions, OG/Twitter cards with A/B variations. |
| [`seo/schema-markup-generator`](seo/schema-markup-generator/) | JSON-LD structured data — FAQ, HowTo, Article, Product, LocalBusiness. |
| [`seo/setup-cms`](seo/setup-cms/) | Connect WordPress, Strapi, Contentful, or Ghost. |

### Cross-model

| Skill | What it does |
|-------|-------------|
| [`gemini`](gemini/) | Second opinion from Google Gemini — review, challenge, or consult. |

### Coming soon (`geo/`)

- `geo/entity-builder` — Wikidata, social account creation, parasite property setup
- `geo/persona-content` — real-device persona infrastructure → published content
- `geo/parasite-distribution` — Reddit, Quora, Medium, Notion playbook
- `geo/ai-overview-tracker` — AI Overview + Perplexity + ChatGPT citation monitoring
- `geo/llm-mention-audit` — current LLM citation landscape per client

## Install (development)

Private plugin, installed in dev mode:

```
/plugin marketplace add file:///<absolute-path-to-this-repo>
/plugin install mentionstack@dataatms
```

## Connectors

Most skills depend on:

- **DataForSEO** — `DATAFORSEO_LOGIN`, `DATAFORSEO_PASSWORD` from `ventures/mentionstack/.env.local`
- **Gemini CLI** — installed locally (for `gemini/` skill)

## How it works

Each skill is a `SKILL.md` file with optional `references/`, `scripts/`, and `evals/`. See [`CLAUDE.md`](CLAUDE.md) for the contributor's view — naming, registration, versioning conventions.

```
mentionstack-plugin/
├── .claude-plugin/
│   ├── plugin.json              <- registry of skills
│   └── marketplace.json         <- marketplace metadata
├── seo/
│   ├── content-writer/
│   ├── keyword-research/
│   ├── meta-tags-optimizer/
│   ├── schema-markup-generator/
│   ├── seo-analysis/
│   ├── setup-cms/
│   └── shared/                  <- business-context, preamble
├── gemini/
├── bin/                         <- shared scripts
├── CHANGELOG.md
└── VERSION
```

## License

Proprietary — Mentionstack internal use only.
