---
name: requirements-restful-booker
description: Task requirements for the Restful-Booker API Test Automation task.
---

# Task: Restful-Booker API Test Automation

## System Under Test

Restful-Booker API — a public API for booking management with token-based and basic
authentication, supporting full CRUD operations.

- API documentation: `https://restful-booker.herokuapp.com/apidoc/index.html`

## Task Description

Study and analyze the API. Implement automated tests for the target API, based on the
requirements and user stories below.

## Requirements

- Use Playwright MCP and/or manual exploration to analyze API documentation and generate
  TypeScript interfaces/types.
- Implement a Service layer abstracting API calls, using Copilot or manually as preferred.
- Apply design patterns and principles (e.g., Dependency Inversion, Builder, Factory for
  data), with or without AI assistance.
- Integrate Faker.js for dynamic booking data, either with AI assistance or manually.
- Integrate ESLint, Prettier, and Husky to improve code quality and enable pre-commit checks,
  resolving issues with or without Copilot.
- Implement Allure reporting.
- Use GitHub for version control, GitHub Actions for CI, and optionally Copilot for code
  suggestions.
- Create a CI pipeline that runs tests, lints code, and generates reports.

## User Stories

- As a tester, I want to implement authentication (using either AI-generated code or my own
  solution) and document my approach.
- As a tester, I want to create, update, and delete bookings, experimenting with both
  AI-assisted and manual test generation.
- As a tester, I want to handle negative scenarios (e.g., invalid tokens, malformed JSON),
  optionally brainstorm edge cases with AI, and compare them against my own ideas.
- As a tester, I want to generate and view Allure reports for all test runs.
- As a tester, I want the pipeline to fail if linting or tests fail, and to upload the Allure
  report as an artifact.

## Note

Shared technical standards (language, patterns, infrastructure) and the Definition of Done
are the same across all tasks in this program. They are not repeated here — see the
`requirement-engineer-standards`, `software-engineer-standards`, and
`test-automation-engineer-standards` skills.