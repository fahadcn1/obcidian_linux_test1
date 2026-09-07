---
title: "Linux Project Vault — LLM Context Index"
created: 2026-09-07
updated: 2026-09-07
tags: [index, llm-context, projects, vault-root]
---

# Linux Project Vault

This vault tracks Linux-based personal projects, research, and reference material. It is designed so that any LLM (or future me) can read this one note and immediately know what is being worked on.

> **For LLMs**: Start here. Read this index, then read the project notes linked below. Check `#status/active` for current work and `#status/done` for completed work.

---

## Vault Structure

| Folder | Purpose |
| :--- | :--- |
| `Projects/` | One note per project. Named exactly like the project folder. |
| `Reference/` | Reusable snippets, commands, configs, API notes. |
| `Daily/` | Daily logs and quick scratch that should survive. |
| `Archive/` | Completed, paused, or abandoned projects. |
| `Templates/` | Note templates for new projects and daily logs. |
| `AGENTS.md` | Vault governance rules — read before editing. |

---

## Active Projects

| Project | Status | Short Description | Last Updated |
| :--- | :--- | :--- | :--- |
| [[Projects/fb_manager\|fb_manager]] | #status/active | Facebook comment moderator using browser automation + LLM sentiment analysis. | 2026-09-07 |

---

## Recently Updated

- [[Projects/fb_manager]]
- [[AGENTS.md]]

---

## How to Add a New Project

1. Copy `Templates/project_template.md` to `Projects/<project_name>.md`.
2. Fill in summary, status, tech stack, and source path.
3. Add a row to the Active Projects table above.
4. Link related notes with `[[...]]`.

---

## Status Tags

- `#status/active` — currently being worked on
- `#status/paused` — on hold
- `#status/done` — completed
- `#status/archive` — moved to `Archive/`
