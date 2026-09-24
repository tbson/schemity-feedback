# Schemity Roadmap

What we recently shipped, what we are building, and what we are considering. This page exists so you can see where [Schemity](https://schemity.com) is heading - and influence it: if something in "Considering" matters to you, [open a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+) or vote with a 👍 on the existing issue.

## Recently shipped

- **MCP server for AI agents** (v2.11.0, v2.11.1) - replaces the in-app AI chat: the agent you already use reads your schema, analyzes pending changes, and stages diagram edits you review in History before saving, with setup snippets for Claude Code, Claude Desktop, Cursor, Codex, and OpenCode
- **Change preview** (v2.11.1) - a read-only picture of a migration or your own pending edits, marking dropped, added, altered, and renamed tables and columns with the foreign keys they affect; an agent can draw one on the canvas too
- **Impact analysis** (v2.11.0) - a pending migration, or a hand-written or ORM-generated migration file, checked against the connected database for data loss, failing statements, rewrites, locks, and dependent objects before anything runs
- **Nine more lint rules** (v2.11.1) - twenty-six in all, including the first architecture rule reading context views, plus a Lint Rules tab that explains, searches, and sorts every rule
- **Virtual and inferred relations** (v2.10.2) - document the dependencies a database never declares, drawn with their own dash and kept out of migrations, and have them inferred from column naming on import and refresh
- **Generated columns** (v2.11.1) - GENERATED ALWAYS AS and SQL Server computed columns read on every database and drawn as `= expression`
- **Japanese and Simplified Chinese** (v2.10.0) - the whole interface, picked from a globe dropdown and applied instantly with no reload; generated SQL, migrations, and the data dictionary stay English on purpose, so the same schema exports to the same file in every language
- **Database passwords from a shell command** (v2.10.0) - a credential source toggle runs your own helper on connect and uses its output as the password, which covers AWS RDS IAM tokens, Vault dynamic secrets, and password managers without vendor-specific code

## Building now

- **More lint rules** - schema lint is incremental by design. Still open: rules that need the live connection (counting duplicates before an ALTER, NOT NULL without a default on a populated table), the remaining architecture rules that read context views, an auto-fix that turns a finding into a reviewed migration, and stable public rule ids to use as documentation anchors

## Considering

If any of these matter to you, open a feature request or vote with a 👍 on the existing issue - that is exactly what moves them up this list.

- **Headless CLI** - render SVG/PNG, emit SQL or DBML from the diagram file, and a CI check that fails when the committed ERD drifts from a target database
- **Large-schema abstraction** - collapse entities to title-only or keys-only, and a focus mode that dims everything not connected to the selected entity (the minimap half of this shipped in v2.9.0)
- **Pre-sync drift preview** - before a re-sync applies, a reviewable summary of what will be added, changed, and removed
- **File-vs-file schema diff** - diff two versions of a diagram file (or two git commits) into a visual changelog and generated ALTER statements
- **Notation switching** - numeric/min-max cardinalities as an alternative to crow's foot

---

This roadmap is directional, not a commitment - priorities shift based on the feedback in this repository. Release details land in the [changelog](CHANGELOG.md) when features ship.
