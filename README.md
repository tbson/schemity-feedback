# Schemity Feedback and Community

Welcome to the official community feedback repository for [Schemity](https://schemity.com)! This is the best place to report bugs, request new features, and provide feedback to help us improve the application.

## About Schemity

**Schemity** is a cross-platform ERD tool built for domain-driven database design. Model your domain visually, define bounded contexts, and turn your ERD into real SQL migrations — in a 9 MB native app that works offline. Think in domains, not in DDL.

### What makes Schemity special?

**Relation as First-Class Citizen**
Full routing control, bend points, self-referencing, and advanced snapping. Create foreign keys by dragging fields between entities — 1:N, 1:1, or N:N with auto-generated junction tables. Color-coded connection lines inherit entity colors, and smart routing avoids overlaps while giving you full control through custom waypoints.

**Developer-First Simplicity**
Drag to create a relation. Opinionated defaults — snake_case, auto FK naming, auto junction table. No DBA knowledge required. Full keyboard navigation with vim-style shortcuts, multiple tabs for working across bounded contexts, copy/paste entities between diagrams, and unlimited undo/redo. Entity templates codify common domain patterns.

**Migration Generation**
Compares your ERD to the live database and generates the exact SQL diff — nothing more, nothing less. Connect to MySQL, PostgreSQL, or SQL Server through direct or SSH connections. Reverse-engineer existing databases into ERD diagrams, evolve the design visually, then apply migrations directly. Or work in ERD-only mode for pure domain modeling.

**Git-Native Collaboration**
Clone to offline ERD, commit, team pulls. A long-lived ERD that evolves with your codebase — not locked in a cloud service. Workspace separation isolates ERDs per project, so you push diagrams to git alongside the code they belong to.

**Local-First, Data Transparent**
Plain JSON files in ~/schemity/ — readable, backupable, portable. You own your data completely. No cloud dependency, no vendor lock-in.

**Constraints as First-Class Citizens**
Unique constraints, check constraints, indexes, and not-null rules are all part of your visual design — not afterthoughts buried in migration files. Smart color indicators make multi-column unique constraints immediately visible, so domain invariants stay front and center.

**9 MB Bundle**
No JVM, no Electron, no Chromium. Built with Native WebView and Rust — fast to download, instant to launch. Fully offline, air-gapped, behind VPN. No internet connection required — ever. Native apps for macOS, Windows, and Linux (Ubuntu family).

Whether you're architecting a new system from domain concepts, maintaining a growing schema, or aligning your database with your domain model — Schemity bridges the gap between how you think about your data and how it lives in the database.

## Feature List

### Connection & Database Support
- Managing connections by workspace.
- Allow sorting workspaces and connections by drag and drop.
- Support for multiple database types: MySQL, PostgreSQL, SQL Server.
- Support direct, SSH connections and ERD only mode for pure designing.
- Easy to backup and restore connections/diagrams: Workspace is folder on home directory and ERD data is a json file.
- Workspace separation allows isolating ERDs that need to be pushed to git for sharing, instead of copying them around to other repositories or committing unrelated ERD files.
- Support MacOS, Windows and Linux (.deb and AppImage).

### Auto Update and Licensing
- Auto update to ensure users always have the latest features and bug fixes without manual intervention.
- Only apply update when user click update button to avoid interrupting user's work. User can choose to skip the update and update later.
- Clean release notes to let user know what are the new features and bug fixes in each release.
- Casual license check to ensure user have valid license, but no annoying pop up or block on using the app when license expired. Ensure minimal license check request. User can click on license status to open license management page to update license.
- Complete free for education use, with easy way to verify education status. Free trial for commercial use.

### ERD Diagram Design
- Support dark mode and light mode.
- ERD diagram designing with drag and drop.
- Generate ERD diagram from existing database.
- Export ERD diagram to image file.
- Auto resize entity to fit fields content.
- Support snap to guide (from edges and center of entities) when moving entities/relationships on diagram.

### Field Management
- Reorder fields by drag and drop.
- Set unique, not null, default value for fields.
- Extract default values from check constraints.
- Smart color display for unique/unique together fields to ensure clear visibility for one fields that can be part of several unique constraints.
- Auto position new normal fields at the end of field list but always above created_at/updated_at timestamps fields.
- Auto position new foreign key fields at the bottom of the last existing foreign key.

### Relationships & Foreign Keys
- Create foreignkey by drag and drop field to another entity, support 1:N, 1:1 and N:N with junction table.
- Support self-referencing foreign key.
- Support set color for entities, that color apply on entity's relationship lines too to ensure clear visibility on large diagrams.
- Smart connection lines to avoid overlapping on complex diagrams. User can fully control the connection lines by adding custom waypoints.
- Smart remove relationship line point / line shape by double click on relationship point or line.
- Smart highlight relationship lines / foreign key when clicking on the relationsip or foreign key.

### Database Schema & Migrations
- Generate SQL migration from ERD diagram changes.
- Can apply migration directly to database.
- Support managing check constraints, unique together constraints and indexes.

### Productivity Features
- Support create entity template to pre-define fields for new entities.
- Support quick search entities by name.
- Support quick reference hotkeys.
- Support creating legend box to add notes/groups on diagram. Legend can customize background color and border color.
- Support attach/detach legend to let dragging legend together with entities when they are attached. Support manual detach legend to move independently from entities.
- Support escape path from active field to entity to legend allow user can select parent object by just keep pressing escape key without moving mouse to click on parent object.
- Support moving entity/legend in small steps (1px each) or in bigger steps (20px each) by holding modifier key when using arrow keys.
- Support multiple tabs to work on multiple diagrams in same time.
- Support copy/paste entities/legends between diagrams/tabs.
- Support undo/redo actions.
- Allow user to create fields continuously without closing dialog.

### Keyboard Shortcuts & Navigation
- Support hot key on evey actions (delete, undo, redo, copy, paste, save...).
- Support navigation shortcut keys to move entities (use arrow keys or h/j/k/l keys like vim mode).
- Support navigate highlighted field by using up/down or k/j keys like vim mode.
- Navigate between tabs using Cmd/Ctrl + number (1-9) to quickly switch diagrams.
- Close active tab using Cmd/Ctrl + W.

---

👉 [Download at schemity.com](https://schemity.com/#platforms)

## How to Contribute

We use GitHub Issues to track all feedback. This is the primary way to get in touch with the development team.

-   **Report a Bug:** If you've found a bug or an issue with the application, please [create a new bug report](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=bug&template=bug_report.md&title=%5BBUG%5D+).
-   **Request a Feature:** Have a great idea for a new feature? We'd love to hear it. Please [submit a feature request](https://github.com/tbson/schemity-feedback/issues/new?assignees=&labels=enhancement&template=feature_request.md&title=%5BFEATURE%5D+).
-   **General Feedback & Questions:** For general feedback, questions, or discussions, feel free to [open a new issue](https://github.com/tbson/schemity-feedback/issues/new).

Before creating a new issue, please search the existing issues to see if your feedback has already been reported.

## What to Expect

We will do our best to respond to new issues in a timely manner. Please provide as much detail as possible when creating an issue, as this helps us understand and address your feedback more effectively.

Thank you for helping us make Schemity better!
