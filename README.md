# Codex Assistant

Personal repository for customizing a Codex agent with reusable skills, workflow guidance, and a local knowledge base.

The goal is to keep agent behavior explicit and portable: skills define how Codex should act in repeatable workflows, while the knowledge base stores persistent project notes, research context, and personal operating preferences that should be easy to inspect and maintain.

## What This Repo Contains

```text
.
+-- skills/
|   +-- README.md
|   +-- <skill-name>/
|   |   +-- SKILL.md
|   |   +-- agents/
|   |   +-- references/
|   |   +-- scripts/
|   +-- ...
+-- knowledge-base/
    +-- 00-home/
    +-- 01-literature/
    +-- 02-concepts/
    +-- 03-projects/
    +-- 04-courses/
    +-- 05-writing/
    +-- 06-meetings/
    +-- 07-daily/
    +-- 08-reviews/
    +-- 09-preferences/
    +-- 10-bases/
    +-- 90-templates/
    +-- 99-attachments/
    +-- .obsidian/
```

## Main Areas

| Area | Path | Purpose |
| --- | --- | --- |
| Skills library | `skills/` | Reusable Codex skills, each stored in its own folder with a `SKILL.md` entrypoint. |
| Skill index | `skills/README.md` | Human-readable catalog of available skills and their intended use cases. |
| Knowledge base | `knowledge-base/` | Obsidian-compatible space for long-term notes, project memory, research context, and personal agent preferences. |

## Current Skill Groups

| Group | Skills | Use Case |
| --- | --- | --- |
| Engineering workflow | `andrej-karpathy-skills`, `work-overtime` | Stronger coding discipline, scoped implementation, verification, and autonomous long-running work. |
| Frontend and visual work | `frontend-design`, `portrait-id-photo-skill` | Polished frontend interfaces and specific image-generation workflows. |
| Agent tooling | `mcp-builder`, `defuddle` | MCP server development and clean extraction of web-page content. |
| Obsidian and knowledge work | `obsidian-cli`, `obsidian-markdown`, `obsidian-bases`, `json-canvas` | Reading, writing, structuring, and visualizing notes in an Obsidian-style vault. |

See `skills/README.md` for the detailed skill catalog.

## Skill Format

Each skill should be self-contained and easy for Codex to apply without loading unrelated context.

```text
skills/<skill-name>/
  SKILL.md          # Required entrypoint with metadata and workflow instructions
  agents/           # Optional model or agent configuration
  references/        # Optional supporting documentation
  scripts/           # Optional helper scripts
  examples/          # Optional examples or fixtures
  LICENSE.txt        # Optional license file when copied from another source
```

A good skill should:

- Cover one repeatable workflow.
- Start with clear frontmatter: `name` and `description`.
- Include concrete trigger conditions so Codex knows when to use it.
- Prefer checklists, commands, examples, and validation steps over vague advice.
- Keep large reference material in `references/` instead of overloading `SKILL.md`.

## Knowledge Base

`knowledge-base/` is the persistent academic memory layer for this agent. It is initialized as an Obsidian-compatible vault with dashboards, literature notes, concepts, project records, writing notes, meeting notes, daily capture, review notes, templates, and Bases views.

Current structure:

```text
knowledge-base/
  00-home/          # Dashboards and navigation
  01-literature/    # Papers, books, articles, and reading queue
  02-concepts/      # Reusable academic and technical concept notes
  03-projects/      # Research projects, repos, experiments, and deliverables
  04-courses/       # Coursework, lectures, assignments, and exams
  05-writing/       # Drafts, outlines, statements, and submissions
  06-meetings/      # Supervision, PI meetings, collaboration logs
  07-daily/         # Daily capture notes
  08-reviews/       # Weekly and milestone reviews
  09-preferences/   # Durable user and Codex operating preferences
  10-bases/         # Obsidian Bases for structured academic review
  90-templates/     # Reusable note templates
  99-attachments/   # PDFs, figures, and other artifacts
```

Recommended usage:

- Store durable context that should survive across sessions.
- Start from `knowledge-base/00-home/Home.md`.
- Prefer concise Markdown notes with frontmatter, clear titles, and wikilinks.
- Keep private credentials, API keys, tokens, and account secrets out of the repo.
- Separate stable preferences from temporary task notes.
- Use the templates in `knowledge-base/90-templates/` for repeated academic note types.
- Use the Bases in `knowledge-base/10-bases/` to review literature, projects, writing, and meetings.

## Using This Repository

1. Add or update skills under `skills/<skill-name>/`.
2. Add persistent notes under `knowledge-base/`.
3. Keep the root README focused on the overall system.
4. Keep `skills/README.md` focused on the skill catalog.
5. Commit only the skills and knowledge files that should be portable.

If a Codex runtime expects skills in a specific installation directory, use this repository as the source of truth and copy or symlink selected skill folders into that runtime's skills directory.

## Maintenance Conventions

- Keep every skill folder independently understandable.
- Update `skills/README.md` whenever a skill is added, removed, or renamed.
- Add examples or scripts only when they make the workflow easier to verify.
- Prefer small, composable skills over broad all-purpose instructions.
- Record important project knowledge in Markdown rather than leaving it only in chat history.
- Treat the repository as synchronized when local and remote commits match; ignored system or cache files such as `.DS_Store` do not count as repo changes that need to be synced.

## Roadmap

- Expand `knowledge-base/` with project, research, workflow, and preference notes.
- Normalize skill metadata and catalog fields across all skill folders.
- Add examples for high-value skills.
- Add lightweight validation checks for skill frontmatter and required files.
