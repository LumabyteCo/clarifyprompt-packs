# ClarifyPrompt Knowledge Packs

Community-curated **knowledge packs** for [clarifyprompt-mcp](https://github.com/LumabyteCo/clarifyprompt-mcp) — the open-source MCP prompt compiler.

A **knowledge pack** is a markdown document with optional YAML frontmatter that teaches ClarifyPrompt something durable: a brand voice, a coding convention, a compliance rule, a domain-specific prompting pattern. Packs get chunked, embedded, and made available for semantic retrieval in every subsequent `optimize_prompt` call — scored by the Context Curator against the available token budget.

## Using a pack

In any MCP host wired to `clarifyprompt-mcp@1.3+`:

```
load_knowledge_pack({
  source: "https://raw.githubusercontent.com/LumabyteCo/clarifyprompt-packs/main/packs/nextjs-14-best-practices.md",
  scope: "user"
})
```

Or clone this repo and load locally:

```
load_knowledge_pack({ source: "./packs/anthropic-brand-voice.md" })
```

## Authoring a pack

Packs are plain markdown with YAML frontmatter:

```markdown
---
name: my-team-style-guide
version: 1.0.0
description: Brand + voice guidelines for MyTeam's marketing copy
scope: user
author: My Name
license: Apache-2.0
tags: [brand, voice, marketing]
---

# My Team Style Guide

## Tone
...

## Register
...
```

Rules:
- **H1 = the pack title** (implicit, from the filename or frontmatter).
- **H2+ define chunk boundaries.** Each H2 section becomes one (or more) retrievable chunks. Aim for ~500–1500 chars per chunk.
- **Be specific and actionable.** Packs that teach abstract principles don't retrieve as well as packs with concrete rules and examples.
- **Keep it under ~15 KB.** Larger packs still work but lose retrieval precision as chunks dilute.

## Contributing

1. Fork + branch.
2. Add your pack under `packs/`.
3. Validate with the [schema](./schema/pack.schema.json) (coming in 1.3.1).
4. Open a PR with a short description of what the pack teaches and when to load it.

All packs in this registry are **Apache-2.0** unless explicitly dual-licensed in their frontmatter.

## Starter packs

| Pack | Scope | What it teaches |
|---|---|---|
| [nextjs-14-best-practices](./packs/nextjs-14-best-practices.md) | user | Server-first Next.js 14 App Router conventions |
| [anthropic-brand-voice](./packs/anthropic-brand-voice.md) | user | Anthropic's public-facing tone, register, word choices |
| [sox-compliance](./packs/sox-compliance.md) | user | Sarbanes-Oxley 404 guardrails for AI-assisted financial work |

## License

Apache-2.0 for the registry scaffolding; individual packs retain the license declared in their frontmatter.
