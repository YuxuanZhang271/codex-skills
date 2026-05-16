# Agent Instructions

## Idea Management

- Store ideas under `knowledge-base/20-ideas/`.
- Keep `knowledge-base/20-ideas/Ideas Index.md` as the only index for ideas.
- When the user asks to add an idea, create one new Markdown file directly under `knowledge-base/20-ideas/` for that idea.
- After creating the idea note, update `knowledge-base/20-ideas/Ideas Index.md` with a wikilink to the new idea note.
- Do not create idea subfolders.
- Do not modify any other files when adding an idea, unless the user explicitly asks for broader changes.

## Work Management

- Store work notes under `knowledge-base/30-work/`.
- Keep `knowledge-base/30-work/Work Index.md` as the only index for work.
- When an idea becomes work, create one new Markdown file directly under `knowledge-base/30-work/` with the same title as the idea note.
- Use the work note to store the GitHub repo link, concrete plan, progress, status, and next action.
- Do not create work subfolders.
- Do not store source code, generated project files, datasets, or implementation artifacts in the knowledge base; those belong in a dedicated GitHub repository.
- After creating or updating a work note, update only `knowledge-base/30-work/Work Index.md` unless the user explicitly asks for broader changes.

## Output Management

- Store final outputs under `knowledge-base/40-output/`.
- Keep `knowledge-base/40-output/Output Index.md` as the only index for outputs.
- By default, output storage is for paper PDFs only.
- When adding an output, place the paper PDF directly under `knowledge-base/40-output/` and update `knowledge-base/40-output/Output Index.md` with a link and short label.
- Do not create output subfolders.
- Do not store drafts, source code, slide source files, project files, or other artifacts in output unless the user explicitly asks for them.

## System Management

- Keep `knowledge-base/50-system/System Index.md` as the only system note by default.
- Put durable agent behavior rules in this `agent.md` file rather than creating extra system notes.
- Do not create system subfolders unless the user explicitly asks for a broader system structure.

## Template Management

- Keep templates minimal.
- Default templates are `Idea Note`, `Work Note`, `Paper Note`, and `Reading Queue Item`.
- Do not add new templates unless the user explicitly asks or a repeated workflow clearly needs one.

## Attachment Management

- Keep `knowledge-base/99-attachments/Attachments Index.md` as the only attachment note.
- Do not create attachment subfolders by default.
- Paper PDFs belong in `knowledge-base/40-output/`, not `knowledge-base/99-attachments/`.
- Do not store credentials, source code, datasets, generated project files, or implementation artifacts in attachments.
