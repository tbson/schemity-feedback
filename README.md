# Schemity Feedback and Community

Welcome to the official community feedback repository for [Schemity](https://schemity.com) - the **database design software for software engineers**. This is the best place to report bugs, request new features, and provide feedback to help us improve the application.

## How to Contribute

We use GitHub Issues to track all feedback. This is the primary way to reach the development team.

- **Report a bug:** [create a new bug report](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=bug&template=bug_report.md&title=%5BBUG%5D+)
- **Request a feature:** [submit a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+)
- **General feedback and questions:** [open a new issue](https://github.com/tbson/schemity-feedback/issues/new) or join the [Discord community](https://discord.gg/DVgaXN52ex)

Before creating a new issue, please search the existing issues to see if your feedback has already been reported.

Also in this repository:

- **[Roadmap](ROADMAP.md)** - what recently shipped, what we are building, and what your feedback can influence
- **[Changelog](CHANGELOG.md)** - release notes for every version
- **[Example schemas](examples/)** - importable sample workspaces, in Schemity's plain-JSON format plus DBML and SQL

## What is Schemity?

**Schemity** is database design software for software engineers that turns your live database into a local architecture map. Understand your schema, see the impact of every change, and design the next one: connect a database and Schemity draws every table, inferring the foreign keys it never declared; give your AI agent the same schema through a local MCP server; and review every schema change, yours or your agent's, with lint, dependency impact, and the exact migration SQL before anything is applied. Diagrams are plain JSON files on your own machine, so they live in Git next to your code. No schema upload, no subscription.

Supported databases: **PostgreSQL, Supabase, MySQL, MariaDB, SQL Server, and SQLite**. Runs on macOS, Windows, and Linux.

- Website: [schemity.com](https://schemity.com)
- Documentation: [schemity.com/doc](https://schemity.com/doc)
- Blog: [schemity.com/blog](https://schemity.com/blog)
- FAQ: [schemity.com/faq](https://schemity.com/faq)
- Free online version (design and share only): [lite.schemity.com](https://lite.schemity.com)

## What makes Schemity different?

Most database design software is a drawing canvas that lives in a browser. Schemity is a desktop app wired to the database it describes, and everything below holds whether the hands on the diagram are yours or your AI agent's.

**It reads your database, and keeps up with it.**
Browser tools take your schema as text you paste in, so the diagram starts drifting the moment the next migration lands. Schemity opens a real connection, reverse engineers the schema, and re-syncs every time you open the diagram: entities keep the layout you gave them, dropped tables disappear, and new ones arrive ready to place. Foreign keys the database never declared are inferred from column names and drawn dashed.

**Whatever your agent changes, you see it before it runs.**
An agent can edit the diagram over MCP, or write a migration in your codebase the way your ORM does. Either way the change is drawn without running it - dropped tables in red, new ones in green, changed columns tinted - and impact analysis says what it does to real data: lost rows, failing statements, table rewrites, and dependent views. Nothing writes to the database until you click Migrate, and on a Production connection you type the database name first.

**Your agent gets Schemity, not your credentials.**
Most database MCP servers hand the agent a connection string and run whatever SQL it writes. Schemity is the governed path instead: a local MCP server with no vendor cloud in the middle, every agent edit staged in History for you to review, and the schema going only where your agent already sends your code. It works with Claude Code, Claude Desktop, Cursor, Codex, OpenCode, or any MCP host.

**From a legacy database to a domain map.**
Break a large schema into context views - auth, billing, analytics - while the main diagram stays the single source of truth; turn legends into context views in one click. Then open the Context Map: each domain becomes a node, and each arrow counts the real foreign keys between them, so the architecture itself is a diagram too.

**The diagram is a file you own.**
Schemity writes plain JSON into a folder you choose, so a reorganization by your agent is [reviewed in a pull request](https://schemity.com/blog/erd-lives-in-your-git-repo/) as a diff, like any other change: versioned, branched, and revertible.

**You can only draw what a database would accept.**
A foreign key targets the parent's primary key, cardinality follows that key's uniqueness, referential actions are set per relationship, and duplicate table names are refused - so a diagram that looks valid is valid. Schema lint then checks twenty-six classes of problem and marks them on the diagram itself.

**One purchase, and no meter on your model.**
No per-seat subscription and no cap on tables, diagrams, workspaces, or context views - [no reason to merge two entities to stay under a quota](https://schemity.com/blog/your-erd-tool-shouldnt-count-your-tables/).

**Nothing for us to leak.**
We store an auto-generated device ID and your country, for licensing and regional support, and nothing that identifies you. Payments go through LemonSqueezy, so a SOC 2 or ISO 27001 review finds almost nothing to review.

## Who is Schemity for?

Schemity is for any software engineer who works with relational databases:

- **Starting a new project** - model your domain visually before writing a single migration
- **Joining an existing codebase** - reverse engineer PostgreSQL (or any supported database) into an ERD and understand the schema fast
- **Documenting production** - connect through an SSH tunnel with credentials in the OS keychain or resolved from your own credential helper, read the schema, share the diagram read-only without sharing database access, and export a data dictionary for people who will never open Schemity
- **Evolving a growing schema** - design changes visually, generate precise migrations, keep the ERD in sync with re-sync
- **Consulting and client work** - one workspace folder per client, physically isolated, handed over or deleted as a folder

## How does Schemity compare to other ERD tools?

Honest, detailed comparisons with the tools people usually evaluate alongside Schemity:

- [Schemity vs ChartDB](https://schemity.com/blog/schemity-vs-chartdb) - the offline desktop alternative to the cloud schema visualizer
- [Schemity vs dbdiagram.io](https://schemity.com/blog/schemity-vs-dbdiagram-io) - visual canvas and offline files instead of a DSL in the browser
- [Schemity vs DbSchema](https://schemity.com/blog/schemity-vs-dbschema) - the lightweight alternative to a 100+ engine database IDE
- [Schemity vs DrawSQL](https://schemity.com/blog/drawsql-alternative/) - a live database connection and no table limits instead of a capped browser canvas
- [Schemity vs Lucidchart](https://schemity.com/blog/lucidchart-erd-alternative/) - reverse engineer your database directly instead of hand-exporting a CSV

## Feature List

### Workspaces & Storage
- Multiple workspaces, each a folder on disk; every diagram is a plain local JSON file you can version control with Git
- Manage multiple database connections and diagrams per workspace; reorder by drag and drop
- Import an existing workspace from anywhere on your machine; open the workspace folder in the native file manager with one click
- Workspaces are marked in the list for what they are: a Git branch icon when the folder sits inside a Git repository (at any depth), and its own icon when the workspace was imported from outside the default `~/schemity` folder - the two markers are independent and stack
- Open diagrams in read-only mode - explore a diagram created from a connection without access to that connection
- Move a diagram to another workspace from its right-click menu; a name clash arrives as "Name (2)" rather than overwriting anything
- Diagrams move between the desktop app and Schemity Lite as JSON: export a diagram exactly as it is saved, and import one from the diagram list without overwriting anything - the import picks a free id and carries the suffix into the name. A password never travels in the file

### Database Connections
- PostgreSQL, Supabase, MySQL, MariaDB, SQL Server, and SQLite; multi-schema support on PostgreSQL
- Direct or SSH tunnel connections; test a connection before saving it
- Paste a connection string and the dialog fills itself in - PostgreSQL, MySQL, and SQL Server URIs, a `jdbc:` prefix, and the ADO.NET key/value form the Azure portal hands out; a malformed string is reported rather than half-applied, and every parameter left unused is listed
- TLS verification, not just TLS: verify-ca and verify-full check the server's certificate against a chain, with custom root CA and client certificate files passed through to the drivers
- Passwords stored in the OS keychain, never in plain text; SSH keys stored by reference only; opening a connection asks for the keychain once, not once per command
- Or store no password at all: a credential source toggle runs a shell command through your login shell on connect and uses its output as the password, which is how one mechanism covers AWS RDS IAM tokens, Vault dynamic secrets, and a password manager. Nothing is persisted - the resolved credential lives in memory for five minutes - and a Test command button proves it before you save, reporting only how many characters came back
- Connection setup hides behind a "Connect to a database" link, so a design-only diagram is name, database type, naming, save - with a visible undo that keeps anything already typed
- Environment tags (Local, Stag, Prod) keep the connection list easy to scan; the badge appears on a diagram only when there is a connection behind it
- A protected connection requires typing the database name before a migration can be applied - per connection, on by default for Production - and the migration dialog always shows its target host, database, schema, and environment

### Reverse Engineering & Re-sync
- Design from scratch, or connect to a real database and reverse engineer its schema into an ERD
- Re-sync keeps a reverse-engineered ERD current: reopening the diagram pulls the latest schema, existing entities keep their layout, and a Reset ERD action does the same on demand
- Import SQL (CREATE TABLE statements or a full dump) to generate entities and relationships automatically
- Column comments already in the database are read in as field descriptions and never written back, so an existing schema arrives documented and no refresh overwrites your notes
- Import and export DBML, so schemas move to and from dbdiagram.io and the wider DBML toolchain in one step
- Database views and materialized views are introspected on every supported dialect and shown as read-only entities - italic name, a view or mview label in the footer - and excluded from migration, DBML, and Mermaid output
- A diagram stays editable when its database is unreachable: moving or recoloring an entity still saves, and re-sync reports the unreachable database instead of prompting, leaving your work in progress and its undo history untouched

### Diagram Design
- Dark mode and light mode; entities auto-resize to fit content; smart snapping and marquee multi-select
- The interface is available in English, Japanese, and Simplified Chinese, picked from a globe dropdown beside the theme toggle; switching applies instantly with no reload, and the diagram, the pan position, and every open tab survive it. Generated SQL, DDL, migrations, and the exported data dictionary stay English on purpose, so two people exporting the same schema in different languages still produce the same file to diff
- F10 folds the toolbar and footer away and hands the whole window to the canvas, for screen recording, presenting, or simply a short laptop screen; F9 squares the window off to 16:9
- The canvas cursor names the gesture it is about to perform - each resize handle carries its own direction, the new-relation anchor is a crosshair, a field row is a grab - and stays locked for the length of the gesture
- Entities and legends with no color of their own render in slate and mauve, so a legend and the entities inside it never merge into one hue; colors are suggested from a palette that carries each hue as far as sRGB allows rather than holding every hue down to the dullest one, with lightness fixed per tier so header text flips between black and white on the same line, on the canvas and in the SVG export alike
- Legends group related entities visually - drag, resize, rename, recolor; lock a legend to move its entities with it; right-click a legend to export the SQL of everything inside it
- Two predefined layouts (alphabetical or relationship-based) plus Reset Layout
- Realtime fuzzy search across entity, field, and legend names - type any fragment and jump straight to the match, with each result prefixed by what it is and ordered by match quality
- Search can be scoped to one kind of thing by the same letter the results are labelled with: `[e`, `[f`, or `[l` before the query restricts it to entities, fields, or legends, with the closing bracket and the space optional
- Fields also match on their type, using exactly the text the canvas shows - `VARCHAR(255)` on its length, `TEXT[]` on its array suffix, `[feric` on every NUMERIC column - so you can find the columns that share a shape rather than a name; names still rank above types
- A toggleable minimap shows the whole diagram in miniature with a rectangle marking your viewport: click to jump, drag to pan. Each view carries its own, and entities not yet confirmed by the database are the one thing drawn in color
- An empty canvas points at the way in - right-click and the create-entity shortcut on the main view, import on a context view - and the hint never appears in exports
- Legends and entities support markdown descriptions - a small triangle in the top-right corner opens the rendered description in a modal; context views carry their own, opened from the context view list
- Export diagrams and context views as JPG, PNG, or SVG, export the full SQL, or export a Mermaid erDiagram that renders natively on GitHub, GitLab, Notion, and Obsidian
- A shared diagram opens in the theme its author published it in, applied as a preview so it never rewrites the visitor's own preference; an embed can drop its footer link with `?hidelink=1` while keeping the minimap and theme toggles
- Get SQL and Get DBML read whatever is selected, from the right-click menu, the keyboard shortcut, or the command palette alike, so the SQL or DBML of an arbitrary group of tables is one gesture rather than a table at a time
- SVG exports are true vector documents, not a screenshot wearing an .svg extension: shapes are real shapes grouped per entity and names stay live text, so a diagram opens as editable artwork in Figma, Affinity Designer, Illustrator, or Inkscape
- Export a data dictionary instead of a picture: HTML to print or hand to someone who will never open Schemity, Markdown to commit beside the code, or a six-sheet Excel workbook to filter and sort - every entity and column with its type, key, nullability, default, and description, the unique, check, and index constraints, the relationships with their cardinality and delete rules, and the notes held in legends and context views. Database views are included and labelled, and the export follows the active view, so exporting from a context view documents that context alone
- The data dictionary ends with its own coverage report - how many entities and fields carry a description and the names of those that do not - counting only what you can actually document, so a read-only view's columns are never listed as missing anything

### Context Views
- Focused sub-diagrams of the main ERD: import just the entities for one subject area and arrange them freely
- Read-only by design - the main view stays the single source of truth
- An orange dot marks entities with relationships outside the view, so a focused diagram never hides that it is incomplete
- The boundary indicator on an entity opens a list of everything crossing the view's edge - the keys pointing out and the entities outside referencing it, with each relation's description - and picking a row lands on that entity in the main diagram
- Every context view carries a Main diagram button, and the window title names the view you are in
- Sync from legends gives every legend a context view holding exactly its tables, in one click
- Right-click a legend and choose "Import to context views" - the confirm leads with creating a context view named after that legend and coloured like it, so a legend drawn around a domain becomes a context view in one step; existing context views can be ticked in the same pass

### Context Map
- A bird's-eye view that renders each context view as a single node, with arrows for the dependencies between contexts and a badge showing how many foreign keys flow in each direction; it arranges itself by those dependencies the first time you open it
- Arrow shape encodes dependency health: a straight arrow is a one-way dependency, a curved arrow means two contexts depend on each other - circular dependencies stand out at a glance
- Click a context to highlight all of its dependency arrows; double-click an arrow to see every underlying foreign key behind it
- Each context's color carries over to its node and outgoing arrows, and fuzzy search focuses any context instantly, even on a busy map
- The map is a two-way door: an enter icon on the selected box opens that context view - as does a double click anywhere on the box - a floating Context Map button in every view gets you back, and the map's exit lands on Main, the one view nothing else on the map could reach
- Export the Context Map as JPG, PNG, or SVG, or as a Mermaid diagram

### Fields & Constraints
- Distinct icons for primary keys, foreign keys, and what each plain field holds - text, whole and fractional numbers, booleans, dates and times, JSON, and UUID, with arrays drawing their element's icon inside brackets; nullable and unique badges and default values shown directly on the entity
- Check constraints, composite unique constraints, and indexes managed visually; fields covered by an IN check constraint are underlined, with their allowed values one keystroke away
- Enum columns carry the values their type allows, on PostgreSQL as well as MySQL - read in their declared order and shown as read-only tags, because the values belong to the type rather than to the column
- Convention-aware placement: new fields land above timestamp fields, and a new foreign key lands below the whole key block - under the primary key, any composite primary-foreign keys, and any existing foreign keys - matching the order entities are already laid out in
- Entity templates pre-populate every new table with the fields your team always adds
- Fields carry descriptions of their own, marked by a bar on the leading edge of the row - drawn in SVG exports too - so which columns are documented is a glance rather than an audit; a description is diagram data, never a schema change, so documenting a column produces no migration
- Numeric precision and scale are drawn on the entity - NUMERIC(4,1) reads as NUMERIC(4,1) - and generated columns (GENERATED ALWAYS AS, SQL Server computed columns) are read on every database and drawn as `= expression`
- Array type support for PostgreSQL; smart default values picked from special values or check constraints; Cmd/Ctrl+Enter in the field drawer saves and moves on to the next field

### Relationships & Foreign Keys
- Create foreign keys by dragging a field to another entity - 1:N, 1:1, and N:N with auto-generated junction tables; self-referencing keys supported
- Clear crow's foot notation with configurable cardinality, ON DELETE, and ON UPDATE; an N:N opens at CASCADE on both, since a junction row has no meaning left once either parent is gone, and every dialog reopens on the actions you picked last, remembered separately per relation type
- Relationships with ON DELETE CASCADE are drawn with a bold crow's foot at the child end, so cascading deletes are visible on the canvas without opening any dialog
- Entity colors carry to relationship lines; click a relationship to highlight it together with both connected fields
- Selecting an entity draws every relation touching it at double weight, both ends counted, so its wiring is traceable across a dense diagram at a glance
- The selected relation changes in kind rather than degree - drawn as dots in a fixed contrast color, black on light and white on dark - so it stays findable inside a bundle of parallel lines; the crow's feet and cardinality bars stay solid, and SVG exports are untouched
- Virtual relations document a dependency the database does not declare, using the columns that already carry it: drawn with their own dash, never written to a migration or DBML, and kept through every refresh, rename, and paste
- Undeclared foreign keys are inferred from column naming on connect, refresh, open, and import, arriving as virtual relations that say where they came from; one you delete stays deleted
- Relations carry their own description, drawn along the line and in SVG export; double-click a relation to open its dialog
- Custom waypoints with rounded corners, line hops where lines cross, and double-click gestures to reshape or reset a line; Route Relations runs lines around the tables so they cross less and share corridors as parallel lanes
- Foreign key naming convention (snake_case or camelCase) configurable per connection - applied to the names Schemity writes itself, the foreign key field added when a relation is drawn and the composite keys of a junction table, never to the names you type

### Migrations
- Change the ERD and Schemity generates the SQL migration diff for review; it runs against the connected database only when you explicitly apply it
- Dashed borders distinguish draft entities that do not exist in the database yet
- Impact analysis (F7) checks the pending migration for data loss, statements that can fail on existing rows, table rewrites and locks, and dependent views, triggers, and functions - saying what the database does to each - and shows how far the change spreads through foreign keys and context views; row counts are catalog estimates unless you ask for an exact, read-only count
- Analyze a migration file - pasted or opened, hand-written or generated by Prisma, Alembic, or Flyway - against the connected database without executing any of it
- Change preview (Shift+F7) pictures a migration or your own pending edits: dropped, added, altered, and renamed tables and columns marked on a read-only canvas, with the affected foreign keys and a findings drawer describing the plan in words
- Exported SQL creates tables with their constraints inline - primary keys, unique and check constraints, and foreign keys inside CREATE TABLE, emitted in dependency order, with ALTER statements only where a deferred foreign key needs one

### Schema Lint
- Twenty-six classes of schema problem, checked offline against the diagram and reported on the diagram itself: a colored strip in the margin marks the exact entity and the exact field row, with a count beside entities carrying more than one
- Findings are grouped by consequence - fails at runtime, constraint unenforced, permanent cost, convention worth confirming - rather than graded on a severity scale, and each one jumps to its entity on the canvas or opens the dialog that resolves it
- It knows a correct link table from a broken one: a composite primary key over the foreign key pair and a surrogate id plus a unique constraint on that pair are both accepted, while a multi-column unique containing a nullable column - which enforces nothing, because NULLs compare as distinct - is caught
- A live count badge on the Lint button, colored by the most serious finding, works whether or not the mode is open
- Per-finding ignores and per-rule switches are saved in the diagram file, so the conventions your team agreed on travel with the schema and get reviewed in Git
- The Lint Rules tab explains every rule, searches and sorts them by finding count, and a Copy link on each finding hands it to an AI model in one click

### AI Agents (MCP)
- Schemity is an MCP server, with setup snippets in the MCP drawer for Claude Code, Claude Desktop, Cursor, Codex, OpenCode, and MCP Inspector; `schemity --mcp` runs over stdio and can launch the app itself
- An agent reads your schema, context views, and dependencies - including indirect cycles spanning several contexts - lints it, and analyzes the impact of pending changes or a migration file
- It edits what a person edits - entities, columns, keys, constraints, indexes, relations, legends, and context views - as unsaved changes you review in History (F6) and save yourself; nothing it does writes the diagram file or the database
- It can group entities into legends, route relations, and draw a change preview on the canvas so you see what a change means
- Every undo step an agent makes names the agent that made it

### Keyboard & Productivity
- Shortcuts for nearly every action; Vim-style navigation (h/j/k/l) across entities and fields
- Multiple tabs with isolated undo/redo history; switch with Cmd/Ctrl + 1-9
- Copy/paste entities and fields between diagrams - pasting onto an existing entity transfers layout and color only, so arrangements move between diagrams safely
- A copy stays on the clipboard rather than being consumed by the first paste, and repeated pastes cascade, so putting one entity down three times is one copy and three pastes
- Shift is the multi-select modifier on every platform - Shift+click to add an entity, Shift+drag to box-select - with the platform's own toggle key kept as an alias
- Move entities by keyboard in 1 px or 20 px steps
- History (F6) describes every undo step and when it was made

## Pricing

**$129 one-time** - a one-time purchase ERD tool, not a subscription. Includes 1 year of updates; $69/year to keep receiving updates after that. Your licence never expires and security patches stay free, so the app keeps working forever even if you never renew.

**Free for education** (email support@schemity.com with your .edu address) and a **2-week full trial** for everyone, no credit card. After the trial, offline design keeps working and nothing on your disk is locked away - what pauses is the live-database half and the features built on it, including context views, the minimap, schema lint, impact analysis, and the MCP server, until a licence unlocks them again. Existing workspaces stay usable; only creating a new one is gated. Details on the [pricing page](https://schemity.com/pricing).

---

👉 [Download Schemity at schemity.com](https://schemity.com/#platforms)

## What to Expect

We do our best to respond to new issues in a timely manner. Please provide as much detail as possible when creating an issue - it helps us understand and address your feedback effectively.

Thank you for helping us make Schemity better!
