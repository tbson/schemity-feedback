# Schemity Roadmap

What we recently shipped, what we are building, and what we are considering. This page exists so you can see where [Schemity](https://schemity.com) is heading - and influence it: if something in "Considering" matters to you, [open a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+) or vote with a 👍 on the existing issue.

## Recently shipped

- **Starred diagrams** (v2.14.8) - a Starred group above the workspaces, across every workspace
- **Import Schemity JSON onto a blank canvas** (v2.14.8) - fill an empty diagram from a file, keeping its own connection
- **Standard spacing** (v2.14.8) - tables and legends snap to a 34 px gap from their neighbour and back to the row or column they started on
- **Refresh keeps your edits** (v2.14.7) - a three-way merge brings the database's changes in and keeps yours pending
- **MariaDB as its own database** (v2.14.7) - supported from 11.4, with VECTOR and INVISIBLE columns
- **Tenant-safe foreign keys** (v2.14.5) - a relation to a tenant key becomes a composite foreign key, with ON DELETE SET NULL (column) on PostgreSQL 15+
- **MCP prompts** (v2.14.5) - ready-made agent workflows: organize by domain, review a migration, design a feature
- **CockroachDB as its own database** (v2.14.3) - its own type, INTEGER kept 32-bit, hash-sharded indexes kept, and six CockroachDB lint rules

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
