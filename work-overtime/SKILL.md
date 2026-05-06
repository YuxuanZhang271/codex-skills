---
name: work-overtime
description: "Autonomous long-running software development workflow. Use this skill when the user says they are going to rest, go offline, or wants Codex to keep working independently: plan the work, split implementation across worktrees and subagents when useful, continue development without routine clarification, verify each completed slice, reclaim accepted agents, and report the final outcome."
---

# Work Overtime

## Operating Mode

Treat the user's handoff as:

> I am going to rest. From this point onward, you have full responsibility to plan the work, continue development, and make routine implementation decisions autonomously. Do not ask for confirmation for normal task planning or execution. First create a complete development plan, then delegate independent feature slices to subagents in separate worktrees for parallel development. As each slice passes review and verification, immediately integrate the result and close the corresponding agent.

This grants autonomy over ordinary engineering choices, sequencing, and delegation. It does not override system, platform, repository, security, or tool approval requirements.

## Workflow

1. Build context before planning.
   - Inspect the repository, current branch, worktree state, task surface, existing tests, and user-provided requirements.
   - Identify dirty files and avoid reverting unrelated user changes.
   - Define the exact deliverables and success criteria.

2. Create the execution plan.
   - Use a concise plan with implementation slices, validation checks, integration order, and known risks.
   - Mark one step in progress at a time and update the plan as work advances.
   - Prefer a plan that lets independent slices run in parallel.

3. Split work across worktrees and subagents when useful.
   - Delegate only concrete, bounded, independent tasks with disjoint ownership.
   - Tell each subagent it is not alone in the codebase, must not revert others' edits, and must report changed files and verification results.
   - Keep blocking, tightly coupled, or high-risk integration work local.

4. Continue local development while agents run.
   - Do meaningful non-overlapping work instead of waiting by default.
   - Inspect returned changes, integrate only accepted work, and adjust the plan when evidence changes.
   - Close each agent as soon as its accepted slice is integrated or rejected.

5. Verify before completion.
   - Run the narrowest reliable checks first, then broader tests when the change touches shared behavior.
   - For frontend changes, start the dev server when needed and verify the UI with browser or screenshot checks.
   - Record commands run, failures encountered, and any checks that could not be executed.

6. Finish with a concise handoff.
   - Summarize implemented changes, changed files, validation status, and residual risks.
   - Mention any permission-limited or environment-limited work explicitly.

## Autonomy Rules

- Make routine implementation choices without asking the user.
- Ask only when the task is ambiguous in a way that could cause irreversible damage, security risk, external spending, credential exposure, or a major product-direction change.
- Request platform approvals when required by the runtime, even if the user said permissions are open.
- Do not perform destructive git or filesystem operations unless explicitly requested or separately approved.
- Prefer continuing until the task is handled end to end, including implementation, integration, verification, and cleanup.

## Delegation Template

Use this shape for worker prompts:

```text
You are working in parallel with other agents. Do not revert edits made by others. Own only: [files/modules/responsibility]. Implement [specific slice]. Follow existing repository patterns. Run [checks]. Return changed files, verification results, and any blockers.
```
