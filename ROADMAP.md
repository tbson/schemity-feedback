# Schemity Roadmap

What we recently shipped, what we are building, and what we are considering. This page exists so you can see where [Schemity](https://schemity.com) is heading - and influence it: if something in "Considering" matters to you, [open a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+) or vote with a 👍 on the existing issue.

## Recently shipped

- **Import from other modelling tools** (v2.14.2) - Visual Paradigm, MySQL Workbench, Navicat, DbSchema, and DBML onto a blank canvas, keeping positions and colours
- **Reading-order Auto Layout** (v2.14.2) - parents above or left of their children, the canvas near 3:2, lines routed
- **Cloudflare D1** (v2.14.2) - read a D1 database's schema and row counts over Cloudflare's API, read-only
- **One-click MCP setup** (v2.14.1) - add or remove Schemity in Claude Code, Claude Desktop, Cursor, Codex, and OpenCode with one button
- **CockroachDB** (v2.14.1) - connects as PostgreSQL, with row counts from CockroachDB's own statistics
- **Snowflake live connection** (v2.14.0) - connect read-only with a key pair or access token; Schemity reads the schema, structure-locks the diagram, and shows warehouse drift
- **Vector columns everywhere** (v2.14.0) - pgvector, MySQL 9, SQL Server 2025, and Snowflake vectors keep their dimension, and pgvector HNSW and IVFFlat indexes keep their options
- **Several migration files as one** (v2.13.3) - analyze a Flyway or Prisma folder in order, rollback files left out

## Building now

- **More lint rules** - schema lint is incremental by design. Still open: rules that need the live connection (counting duplicates before an ALTER, NOT NULL without a default on a populated table), the remaining architecture rules that read context views, an auto-fix that turns a finding into a reviewed migration, and stable public rule ids to use as documentation anchors

## Considering

If any of these matter to you, open a feature request or vote with a 👍 on the existing issue - that is exactly what moves them up this list.

- **Headless CLI** - render SVG/PNG, emit SQL or DBML from the diagram file, and a CI check that fails when the committed ERD drifts from a target database
- **Large-schema abstraction** - collapse entities to title-only or keys-only, and a focus mode that dims everything not connected to the selected entity (the minimap half of this shipped in v2.9.0)
- **File-vs-file schema diff** - diff two versions of a diagram file (or two git commits) into a visual changelog and generated ALTER statements
- **Notation switching** - numeric/min-max cardinalities as an alternative to crow's foot

---

This roadmap is directional, not a commitment - priorities shift based on the feedback in this repository. Release details land in the [changelog](CHANGELOG.md) when features ship.
