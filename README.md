---
title: "Linux Project Vault — LLM Context Index"
created: 2026-09-07
updated: 2026-09-07
tags: [index, llm-context, projects, vault-root]
---

# Linux Project Vault

**Purpose**: Track Linux-based personal projects, reference material, and daily logs across machines.

> **For LLMs**: Read this note, then read [[LLM.md]] for navigation and token rules. Read [[AGENTS.md]] before editing. Active work is tagged `#status/active`.

---

## TL;DR

- One note per project in `Projects/`.
- Root index lists status + one-line description for every project.
- `Reference/` holds reusable snippets. `Daily/` holds logs. `Archive/` holds old projects.
- Keep notes atomic. Link instead of duplicating. No secrets. No UI-state commits.

---

## Active Projects

| Project | Status | Short Description | Last Updated |
| :--- | :--- | :--- | :--- |
| [[Projects/fb_manager\|fb_manager]] | #status/active | Facebook comment moderator using browser automation + LLM sentiment analysis. | 2026-09-07 |

---

## Recently Updated

- [[Projects/fb_manager]]
- [[LLM.md]]
- [[AGENTS.md]]

---

## Vault Layout

| Folder / File | Purpose |
| :--- | :--- |
| `Projects/` | One note per project, named exactly like the project folder. |
| `Reference/` | Reusable snippets, commands, configs, API notes. |
| `Daily/` | Daily logs and scratch that should survive. |
| `Archive/` | Completed, paused, or abandoned projects. |
| `Templates/` | Note templates. |
| [[README]] | This index. |
| [[LLM.md]] | Rules for AI assistants. |
| [[AGENTS.md]] | Vault governance. |

---

## How to Add a New Project

1. Copy `Templates/project_template.md` → `Projects/<project_name>.md`.
2. Fill summary, status, tech stack, source path.
3. Add a row to the Active Projects table above.
4. Commit and push.

---

## Status Tags

- `#status/active` — currently being worked on
- `#status/paused` — on hold
- `#status/done` — completed
- `#status/archive` — moved to `Archive/`
