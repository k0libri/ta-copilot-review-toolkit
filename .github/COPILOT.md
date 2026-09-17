# Copilot Customization Files

This folder contains the AI customization files used for self-review of PRs before opening
them for mentor review.

## What's here

| File | Type | Purpose |
|------|------|---------|
| `agents/pr-review.agent.md` | Agent | Orchestrates the full PR review: gets the diff, loads the right requirement, runs all three specialist reviews, merges the result. |
| `skills/requirement-engineer-standards/SKILL.md` | Skill | Checklist: requirement coverage + AI tooling DoD items. |
| `skills/software-engineer-standards/SKILL.md` | Skill | Checklist: architecture, design patterns, DoD items. |
| `skills/test-automation-engineer-standards/SKILL.md` | Skill | Checklist: test design, coverage, CI/CD DoD items. |
| `skills/requirements-restful-booker/SKILL.md` | Skill | Task requirements for the Restful-Booker task. |
| `skills/requirements-automation-exercise/SKILL.md` | Skill | Task requirements for the Automation Exercise task. |

Each agent and skill declares its version in YAML frontmatter. The current toolkit release is
recorded in the repository root [VERSION](../VERSION), with changes recorded in
[CHANGELOG.md](../CHANGELOG.md).

## How to use

In VS Code Copilot Chat, run:

```
@pr-review
```

The agent will ask which task you're working on (if it's not obvious), get your current git
diff, and produce a merged review report grouped by **Critical**, **Should Fix**, and
**Suggestion**.

Run this **before** opening your PR, fix what you can, then open the PR for mentor review.

## Adding a new task

To add a new task type:

1. Create a new folder under `skills/requirements-<task-name>/` with a `SKILL.md` file,
   following the same structure as the existing ones (System Under Test, Task Description,
   Requirements, User Stories).
2. Add a line for it in the `pr-review.agent.md` Step 2 task list.
3. Update the table above.
