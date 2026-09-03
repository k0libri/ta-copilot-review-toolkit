---
name: test-automation-engineer-standards
description: Checklist for reviewing a PR diff from a Test Automation Engineer point of view — test design and CI/CD readiness.
---

# Test Automation Engineer Review Standards

Use this checklist to review a PR diff. Focus only on test design and CI/CD quality. Do not
comment on requirement coverage or code architecture — other specialists check those.

## 1. Test Structure (general best practice)

- **AAA Pattern** — each test should follow Arrange, Act, Assert. Flag tests that mix these
  steps together or are hard to read.
- **Test Independence** — each test must be able to run alone, in any order. Flag tests that
  depend on the state left by another test.
- **Meaningful Test Names** — test names should clearly describe what is being tested and the
  expected outcome.

## 2. Test Coverage (general best practice)

- **Positive Scenarios** — does the diff cover the main "happy path" scenarios from the task's
  User Stories?
- **Negative Scenarios** — does the diff cover invalid input, error handling, and edge cases
  (for example: invalid tokens, malformed JSON, invalid login, out-of-stock purchase,
  depending on the task)? Missing negative coverage should be flagged as **Should Fix**.

## 3. CI/CD & Reporting (Definition of Done)

This is a fixed, program-wide checklist — it is the same for every task. Check the diff (and
repo configuration, if visible) for evidence of:

- **Pre-commit Hooks** — Husky blocks commits that fail ESLint or Prettier.
- **Pull Request** — a pull request is created for the whole framework (not just a partial
  diff).
- **Pipeline** — GitHub Actions runs tests in parallel (sharding enabled) and uploads Allure
  Reports as artifacts.
- **Traceability** — failed CI tests generate a Playwright Trace for review.
- **(Optional)** The Allure Report is automatically published to GitHub Pages from the
  pipeline. Missing this should be flagged only as a **Suggestion**, never Critical or
  Should Fix.

## Output Format

Write your findings as a markdown list. Each item must follow this format:

```
- **[file:line]** — finding — best practice/DoD reference
```

If there are no findings for a category, write "No issues found" under that category instead
of leaving it empty.