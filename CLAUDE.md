# Mentionstack Plugin — Working Notes

Internal Claude Code plugin for Mentionstack. Forked from `nowork-studio/toprank` and being adapted for GEO/AEO-first agency delivery.

## Repository purpose

- Internal toolkit. Private — not currently distributed publicly.
- Houses skills under `seo/` (foundational SEO capabilities) and eventually `geo/` (Mentionstack moat — entity building, persona content, parasite distribution, LLM citation tracking, AI Overview monitoring).
- Skills are namespaced as `/mentionstack:<skill-name>`.
- Registered via `.claude-plugin/plugin.json` (skills list) and `.claude-plugin/marketplace.json` (plugin metadata).

## When adding or modifying a skill

1. Create/edit the skill directory under the appropriate category with a `SKILL.md` containing valid frontmatter (`name`, `description`).
2. **Register it in `.claude-plugin/plugin.json`** under the `skills` array. A skill that exists on disk but isn't listed here will NOT appear in the installed plugin.
3. Bump version in three places so upgrades propagate:
   - `.claude-plugin/plugin.json` → `version`
   - `.claude-plugin/marketplace.json` → both `metadata.version` and `plugins[0].version`
   - `VERSION` file at repo root
4. Update `CHANGELOG.md` with a user-facing note.

## Versioning

Semantic-ish: bump patch for skill additions / fixes, minor for new categories or meaningful capability jumps, major for breaking skill API changes.

## Mentionstack scientific delivery standard (non-negotiable)

Every content-producing skill enforces this. Treat each piece like a CRO test.

- **Hypothesis** — what we expect this content to win
- **Target keywords** — primary + secondary, grounded in DataForSEO data
- **Target LLMs** — which answer engines we're aiming at (ChatGPT, Perplexity, Gemini, AI Overview)
- **Expected outcome** — measurable result (citation, ranking, traffic, conversion)
- **Approval gate** — Dylan or AM sign-off before publish

Outcomes: Won / Lost / Inconclusive.

## Connectors

Skills reference external tools using the `~~category` placeholder pattern so they remain tool-agnostic.

| Category | Placeholder | Purpose |
|----------|-------------|---------|
| DataForSEO | `~~dataforseo` | Keyword volume, SERP shape, competitor analysis, AI Overview tracking, LLM citation data (GEO add-on) |
| Search Console | `~~search-console` | First-party impression/click data per client (Phase 2) |
| CMS | `~~cms` | WordPress, Webflow, Shopify, Strapi, Contentful, Ghost (Phase 2) |

Auth lives in `ventures/mentionstack/.env.local` (gitignored). Skills' bundled scripts load via `os.environ`.

## State directory

`~/.mentionstack/` for cached business contexts, client bibles, eval state, etc.

## Related repos

- Public toprank (`nowork-studio/toprank`) — original upstream. Generic SEO/Ads. Mirror diverges over time as Mentionstack-specific capabilities land.
