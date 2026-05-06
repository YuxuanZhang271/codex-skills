# Codex Skills

Personal collection of Codex skills for coding discipline, frontend design, MCP server development, long-running autonomous work, and image-generation workflows.

## Skills Outline

| Skill | Folder | Purpose | Best Used For | Supporting Files | Original Repo |
| --- | --- | --- | --- | --- | --- |
| Andrej Karpathy Skills | `andrej-karpathy-skills/` | Adds stricter senior-engineer coding discipline: think before coding, state assumptions, keep changes simple and surgical, and verify outcomes. | Careful implementation, bug fixes, refactors, and code review follow-up where scope control matters. | `SKILL.md`, `agents/openai.yaml` | [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) |
| Frontend Design | `frontend-design/` | Guides distinctive, production-grade frontend interface work with strong typography, color, motion, composition, and visual direction. | Building or improving websites, dashboards, React components, UI artifacts, and polished web experiences. | `SKILL.md`, `LICENSE.txt` | [anthropics/skills](https://github.com/anthropics/skills/tree/main/skills/frontend-design) |
| MCP Builder | `mcp-builder/` | Guides creation of high-quality Model Context Protocol servers with well-designed tools, schemas, testing, and evaluations. | Building Python or TypeScript MCP servers that connect LLM agents to external APIs and services. | `SKILL.md`, `LICENSE.txt`, `reference/`, `scripts/` | [anthropics/skills](https://github.com/anthropics/skills/tree/main/skills/mcp-builder) |
| Portrait ID Photo Skill | `portrait-id-photo-skill/` | Defines a precise image-generation prompt for a professional executive ID-style portrait matching a reference layout and typography. | Generating a corporate headshot with fixed subject pose, white background, bottom banner text, and reference-matched styling. | `SKILL.md`, `agents/openai.yaml` | - |
| Work Overtime | `work-overtime/` | Defines an autonomous long-running development workflow for planning, delegation, verification, and final handoff. | Tasks where the user goes offline or asks Codex to keep working independently across multiple implementation slices. | `SKILL.md`, `agents/openai.yaml` | - |

## Repository Structure

Each skill folder should include a `SKILL.md` file with frontmatter metadata and operating instructions. Optional files can add agent configuration, reference material, scripts, examples, or license terms.

```text
skill-name/
  SKILL.md
  agents/
  reference/
  scripts/
  examples/
  LICENSE.txt
```

## Notes

- This repo is intended as a personal Codex skills library.
- Keep each skill focused on one repeatable workflow.
- Add supporting files only when they make the skill easier to apply or verify.
