# Schemity Roadmap

What we recently shipped, what we are building, and what we are considering. This page exists so you can see where [Schemity](https://schemity.com) is heading - and influence it: if something in "Considering" matters to you, [open a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+) or vote with a 👍 on the existing issue.

## Recently shipped

- **Auto increment on every database** (v2.13.1) - set it from the field editor anywhere, with start and step on PostgreSQL, SQL Server, and Snowflake
- **Real-schema round trips** (v2.13.1) - SQL from an imported script or a live database rebuilds the same tables, keys, constraints, and indexes, checked against real PostgreSQL, MySQL, SQL Server, and SQLite schemas
- **Virtual relations menu** (v2.13.1) - show, hide, or remove virtual relations in one place, and turn off inferring them per connection
- **SQL conversion between databases** (v2.13.0) - Get SQL and Export > SQL file write the same tables for PostgreSQL, MySQL, SQL Server, SQLite, or Snowflake, with a report of every changed type, checked against real engines
- **Snowflake for design** (v2.13.0) - draw a diagram or import a `GET_DDL` script, and export a full Snowflake CREATE script
- **PlantUML, D2, OpenAPI, and PDF data dictionary export** (v2.13.0) - plus a preview with Copy and Save for every text export
- **Fetch & merge on open** (v2.13.0) - opening a diagram fetches the live database and merges it as an unsaved change, and a Database changed button previews what changed against your diagram - from another tool or your AI agent - before you save
- **Import SQL that updates** (v2.13.0) - a re-import updates tables already on the diagram, marking each New, Updated, or Unchanged

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
