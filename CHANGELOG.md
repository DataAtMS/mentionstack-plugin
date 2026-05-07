# Changelog

All notable changes to the Mentionstack plugin are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [0.1.0] — 2026-05-07

### Initial scaffold

Forked from `nowork-studio/toprank` v0.13.0. Stripped Google Ads skills, AdsAgent MCP server config, public marketplace branding, and toprank-specific update/test infrastructure. Renamed plugin namespace from `toprank` to `mentionstack` and marketplace owner from `nowork-studio` to `dataatms`.

Skills carried over from toprank as starting points — these will be progressively re-engineered toward GEO/AEO-first delivery using DataForSEO instead of GSC:

- `seo/seo-analysis`
- `seo/content-writer`
- `seo/keyword-research`
- `seo/meta-tags-optimizer`
- `seo/schema-markup-generator`
- `seo/setup-cms`
- `gemini`

State directory moved from `~/.toprank/` to `~/.mentionstack/`.

Removed:
- `google-ads/` (4 skills — Mentionstack is not an ads agency)
- `toprank-upgrade-skill/` (toprank-specific public-marketplace update infra)
- `seo/seo-page/` (orphan, unregistered)
- `bin/toprank-update-check`, `bin/toprank-config`, `bin/toprank-change-watch`, `bin/preamble.md` (public-marketplace update infra)
- `test/`, `conftest.py`, `requirements-test.txt` (toprank-specific test harness — Mentionstack tests will be rebuilt)
- `.mcp.json` (referenced AdsAgent MCP server)
- `server.json` (registry entry for the public AdsAgent server)
