---
title: "LLM.md — For AI Assistants"
created: 2026-09-07
updated: 2026-09-07
tags: [meta, llm, instructions, vault-guide]
---

# LLM.md — For AI Assistants

Read this first if you are an AI helping the owner of this vault.

---

## What This Vault Is

A Linux project knowledge base synced across 2-3 PCs. It tracks:

- Active/paused/done projects (one note per project)
- Reusable reference material (commands, configs, snippets)
- Daily logs and research findings

Golden rule from [[AGENTS.md]]: *If it's not useful tomorrow, it doesn't belong here.*

---

## How to Navigate

1. **Start at [[README]]** — it lists active projects with status and one-line descriptions.
2. **Read only the project notes you need** — do not open every note.
3. **Use tags to filter**:
   - `#status/active` = current work
   - `#status/paused` = on hold
   - `#status/done` = completed
   - `#status/archive` = moved to `Archive/`
4. **Check [[AGENTS.md]]** before adding or editing anything.

---

## Token Budget Rules

Keep reads and writes cheap.

### When Reading

- Prefer tables and bullet lists over long prose.
- Do not read source code files unless explicitly asked. Use the project note summary.
- One project note ≈ one context unit. Avoid chaining more than 3-4 notes per turn.

### When Writing Memory

- **Be atomic**: one idea per note. Link it instead of copying it.
- **Update, don't duplicate**: add to the existing project note; do not create a second note for the same project.
- **Frontmatter first**: always include `title`, `updated`, `tags`, `status`.
- **Keep summaries under 400 words** unless the topic genuinely needs more.
- **Use links**: `[[note_name]]` instead of repeating content.
- **No raw logs**: summarize terminal output, error messages, or research; do not paste full dumps.

---

## Required Steps When Updating a Project

1. Edit `Projects/<project_name>.md`.
2. Update its `updated` field and `status` tag in frontmatter.
3. Add a one-line summary of what changed to the **Recent Changes** section.
4. Update the project's row in [[README]] (last updated date, status, description if it changed).
5. If the change affects the vault itself, update [[LLM.md]] or [[AGENTS.md]].

---

## What NOT to Do

- Do not write chain-of-thought or internal reasoning into vault notes.
- Do not commit `.obsidian/workspace.json`, `graph.json`, or other UI state.
- Do not store secrets (API keys, tokens, passwords) in any note.
- Do not duplicate full code files as vault notes unless explicitly asked.
- Do not leave transient TODOs here — use a task app for those.

---

## Quick Reference

| Folder | Contains |
| :--- | :--- |
| `Projects/` | One note per project |
| `Reference/` | Reusable snippets and configs |
| `Daily/` | Daily logs |
| `Archive/` | Completed or abandoned projects |
| `Templates/` | `project_template.md`, daily log template |
| `README.md` | Root index — start here |
| `AGENTS.md` | Vault governance |
| `LLM.md` | This file |
