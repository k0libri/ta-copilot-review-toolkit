---
name: requirement-engineer-standards
description: Checklist for reviewing a PR diff from a Requirement Engineer point of view — requirement coverage and AI-tooling process compliance.
version: 1.0.0
---

# Requirement Engineer Review Standards

Use this checklist to review a PR diff. Focus only on the points below. Do not comment on
code architecture, design patterns, or test structure — other specialists check those.

## 1. Requirement Coverage

Compare the diff against the Requirements and User Stories from the task skill that was
loaded in Step 2 of the agent workflow.

- Does the diff implement all the Requirements listed in the task?
- Does the diff cover all User Stories listed in the task?
- If something is missing, quote the exact requirement or user story that is not covered.
- If the diff does something that is *not* in the task (scope creep), mention it as a
  **Suggestion**, not a **Critical** issue.

## 2. AI Tooling Integration (Definition of Done)

This is a fixed, program-wide checklist — it is the same for every task. Check the diff for
evidence of:

- **Prompt Documentation** — a `PROMPTS.md` file exists, logging how Copilot/MCP or manual
  approaches were used to solve complex architectural hurdles. If missing, flag as
  **Should Fix**.
- **MCP Usage** — evidence of using Playwright MCP for site exploration and locator
  generation, or documentation of manual alternatives.
- **Automated Healing** — at least one instance of using AI or manual strategies to fix a
  test failure is demonstrated.

## Output Format

Write your findings as a markdown list. Each item must follow this format:

```
- **[file:line]** — finding — requirement/DoD reference (quoted)
```

If there are no findings for a category, write "No issues found" under that category instead
of leaving it empty.