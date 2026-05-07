---
title: Knowledge Base Guide
aliases:
  - Vault Guide
tags:
  - kb/guide
  - academic
status: active
---

# Knowledge Base Guide

This folder is an Obsidian-compatible academic vault for durable research context, literature notes, project records, writing drafts, meeting notes, coursework, and personal operating preferences.

Start from [[00-home/Home|Home]].

## Structure

| Folder | Purpose |
| --- | --- |
| `00-home/` | Dashboards, maps, and navigation entrypoints. |
| `01-literature/` | Paper, book, article, and reading-queue notes. |
| `02-concepts/` | Reusable concept notes and technical explanations. |
| `03-projects/` | Research projects, experiments, repos, and deliverables. |
| `04-courses/` | Coursework, lecture notes, assignments, and exams. |
| `05-writing/` | Paper drafts, application materials, essays, and outlines. |
| `06-meetings/` | PI meetings, group meetings, supervision, and collaboration logs. |
| `07-daily/` | Daily capture notes. |
| `08-reviews/` | Weekly, monthly, and milestone review notes. |
| `09-preferences/` | Stable personal preferences and Codex operating rules. |
| `10-bases/` | Obsidian Bases for structured academic views. |
| `90-templates/` | Reusable note templates. |
| `99-attachments/` | PDFs, images, figures, and exported artifacts. |

## Conventions

- Use wikilinks for internal references, for example [[02-concepts/Embodied AI]].
- Use frontmatter properties consistently so Obsidian Bases can index notes.
- Keep secrets, API keys, tokens, and private credentials out of this repo.
- Put source PDFs or large binary artifacts in `99-attachments/` only when they are meant to be versioned.
- Prefer one durable note per paper, project, concept, meeting, or writing artifact.

## Core Properties

| Property | Use |
| --- | --- |
| `title` | Human-readable note title. |
| `type` | Note type, such as `paper`, `concept`, `project`, `meeting`, `draft`, `course`, or `review`. |
| `status` | Current state, such as `seed`, `active`, `reading`, `drafting`, `blocked`, `done`, or `archived`. |
| `created` | Creation date in `YYYY-MM-DD` format. |
| `updated` | Last meaningful update date in `YYYY-MM-DD` format. |
| `research_area` | Main research area or topic. |
| `tags` | Searchable nested tags. |

## Review Loop

1. Capture raw notes in `07-daily/` or directly in the right folder.
2. Convert useful material into literature, concept, project, or writing notes.
3. Link each note to at least one related note.
4. Review `10-bases/` weekly to update status and priorities.
