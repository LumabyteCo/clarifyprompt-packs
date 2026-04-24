# Contributing a knowledge pack

1. Fork this repo and branch off `main`.
2. Add your pack as `packs/<your-pack-name>.md`.
3. Include YAML frontmatter with at minimum: `name`, `version`, `description`, `license`.
4. Write content that's specific, actionable, and tested in your own workflow.
5. Add a row to the README's starter-packs table.
6. Open a PR.

## Quality bar

- **Does it teach something durable?** A pack that says "be more helpful" isn't useful. A pack that says "when writing SQL for Snowflake, prefer CTEs over nested subqueries and always use `QUALIFY ROW_NUMBER() OVER (...)` for deduplication" is.
- **Is it chunkable?** Each H2 section should stand on its own; don't rely on cross-chunk context.
- **Is it cited?** Reference standards (ASC numbers, RFC specs, framework version), not vibes.

## License

By contributing, you agree your pack ships under Apache-2.0 unless you explicitly dual-license via frontmatter.
