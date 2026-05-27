# 📦 ARCHIVED — packs moved to `clarifyprompt-mcp`

This repository is **archived and read-only**.

Knowledge packs for [clarifyprompt-mcp](https://github.com/LumabyteCo/clarifyprompt-mcp) now live in the engine repo itself, under [`packs/`](https://github.com/LumabyteCo/clarifyprompt-mcp/tree/main/packs).

**To contribute a pack:** open a PR against [LumabyteCo/clarifyprompt-mcp](https://github.com/LumabyteCo/clarifyprompt-mcp). Authoring rules and the quality bar are in [`packs/README.md`](https://github.com/LumabyteCo/clarifyprompt-mcp/blob/main/packs/README.md) over there.

**To load a pack:** in any MCP host wired to `clarifyprompt-mcp@1.3+`:

```
load_knowledge_pack({
  source: "https://raw.githubusercontent.com/LumabyteCo/clarifyprompt-mcp/main/packs/nextjs-14-best-practices.md",
  scope: "user"
})
```

## Why archived?

This registry was created in April 2026 with the right principle in mind (packs are content, not engine code → host them separately so contributions flow independently). After a month at one commit, three starter packs, and zero external PRs, the maintenance overhead of keeping two repos in sync was paying for an audience that hadn't materialized — and the `higgsfield-creative-handbook` pack shipped in `clarifyprompt-mcp@1.6.2` never made it to this registry, exhibit A of the drift.

The split makes sense once there's a forcing function: a community PR queue, pack count >20, or divergent licensing/governance. None of those are true today. Collapsing now keeps the source of truth singular and unambiguous.

See the `1.6.4` entry in [`clarifyprompt-mcp/CHANGELOG.md`](https://github.com/LumabyteCo/clarifyprompt-mcp/blob/main/CHANGELOG.md) for the full rationale.

## Historical contents

The three starter packs hosted here from 2026-04-24 onward — `anthropic-brand-voice`, `nextjs-14-best-practices`, `sox-compliance` — remain authoritative at the engine repo's `packs/` directory, alongside `higgsfield-creative-handbook` (added in 1.6.2). License unchanged: Apache-2.0.

## License

Apache-2.0. See [`LICENSE`](./LICENSE).
