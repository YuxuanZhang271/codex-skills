---
domain: system
title: Knowledge Base Guide
aliases:
  - Vault Guide
tags:
  - kb/guide
  - academic
status: active
---

# Knowledge Base Guide

This folder is an Obsidian-compatible academic vault organized around the lifecycle of academic work: learn from external sources, develop ideas, execute work, publish outputs, and maintain the system.

Start from [[00-home/Home|Home]].

## Structure

| Folder | Purpose |
| --- | --- |
| `00-home/` | Dashboards, maps, and navigation entrypoints. |
| `05-bases/` | Lifecycle Obsidian Bases for structured review. |
| `10-learning/` | External inputs: papers, courses, reading queues, and synthesis notes. |
| `20-ideas/` | Personal research ideas and reusable idea notes, kept flat with one index. |
| `30-work/` | Flat work notes with GitHub repo links, plans, progress, and status. |
| `40-output/` | Paper PDFs and one output index. |
| `50-system/` | One system index; durable agent behavior rules live in `agent.md`. |
| `90-templates/` | Minimal reusable note templates. |
| `99-attachments/` | Supporting vault assets only. |

## Conventions

- Use wikilinks for internal references, for example [[20-ideas/Ideas Index|Embodied AI]].
- Use frontmatter properties consistently so Obsidian Bases can index notes.
- Keep secrets, API keys, tokens, and private credentials out of this repo.
- Put paper PDFs in `40-output/`; use `99-attachments/` only for supporting vault assets explicitly meant to be versioned.
- Prefer one durable note per paper, idea, or work item.

## Core Properties

| Property | Use |
| --- | --- |
| `title` | Human-readable note title. |
| `domain` | Lifecycle domain: `learning`, `idea`, `work`, `output`, or `system`. |
| `type` | Note type, such as `paper`, `course`, `idea`, `work`, `output`, `review`, or `preference`. |
| `status` | Current state, such as `inbox`, `seed`, `active`, `reading`, `drafting`, `blocked`, `done`, or `archived`. |
| `created` | Creation date in `YYYY-MM-DD` format. |
| `updated` | Last meaningful update date in `YYYY-MM-DD` format. |
| `research_area` | Main research area or topic. |
| `tags` | Searchable nested tags. |

## Review Loop

1. Capture raw notes in `20-ideas/` or directly in the right lifecycle area.
2. Promote useful notes through `Learning -> Ideas -> Work -> Output`.
3. Link each note to at least one related note.
4. Review `05-bases/` weekly to update status and priorities.
