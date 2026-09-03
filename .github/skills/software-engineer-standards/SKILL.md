---
name: software-engineer-standards
description: Checklist for reviewing a PR diff from a Senior Software Engineer point of view — code quality, architecture, and design.
---

# Software Engineer Review Standards

Use this checklist to review a PR diff. Focus only on code quality and architecture. Do not
comment on requirement coverage or test design — other specialists check those.

## 1. Core Principles

- **SOLID** — especially Single Responsibility and Dependency Inversion.
- **DRY (Don't Repeat Yourself)** — look for duplicated logic that should be extracted into a
  shared function, class, or fixture.
- **KISS (Keep It Simple)** — flag unnecessarily complex solutions when a simpler one exists.
- **YAGNI (You Aren't Gonna Need It)** — flag code that solves a problem the task did not ask
  for.

## 2. Expected Design Patterns

The program expects these patterns (with or without AI assistance):

- **Page Object Model (POM)** — UI locators and page actions must live in page object
  classes, not directly inside `.spec` files.
- **Service Layer** — API calls must be wrapped in a service/client class, not called
  directly from `.spec` files.
- **Factory / Builder** — test data creation should use factory or builder patterns instead of
  duplicated inline object literals.
- **Dependency Inversion** — high-level modules (tests) should depend on abstractions
  (interfaces/service classes), not directly on low-level implementation details.

## 3. Architectural Excellence (Definition of Done)

This is a fixed, program-wide checklist — it is the same for every task. Check the diff for
evidence of:

- **No Hardcoded Data** — all test data is generated via an AI-guided Data Factory or a
  manually implemented factory. Flag any hardcoded values (URLs, credentials, booking data,
  user data, etc.).
- **Strict Layering** — no direct page or request calls inside `.spec` files; everything must
  go through Service/Page layers.
- **Custom Fixtures** — Playwright fixtures are used to inject Services/Pages into tests,
  instead of instantiating them manually inside each test.

## Output Format

Write your findings as a markdown list. Each item must follow this format:

```
- **[file:line]** — finding — principle/pattern/DoD reference
```

If there are no findings for a category, write "No issues found" under that category instead
of leaving it empty.