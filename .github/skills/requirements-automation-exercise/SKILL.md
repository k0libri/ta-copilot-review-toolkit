---
name: requirements-automation-exercise
description: Task requirements for the Automation Exercise UI + API Hybrid Test Automation task.
version: 1.0.0
---

# Task: Automation Exercise — UI + API Hybrid Test Automation

## System Under Test

Automation Exercise — a public e-commerce demo site with a full UI and backend API.

- Website / API: `https://automationexercise.com/`

## Task Description

Study and analyze the API. Implement automated tests for the target UI and API, based on the
requirements and user stories below.

## Requirements

- Use Playwright MCP and/or manual inspection to generate Page Object Models (POM) with
  optimized locators.
- Implement hybrid testing — use the API to set up test state (e.g., creating a user) and the
  UI to perform actions (e.g., shopping), with or without AI support.
- Configure Playwright Healer Agent and/or manual strategies to identify and fix broken
  selectors during UI updates.
- Apply DRY and SOLID principles, using Copilot Chat for refactoring sessions or manual
  refactoring as preferred.
- Integrate ESLint, Prettier, and Husky.
- Implement Allure reporting.
- Use GitHub, GitHub Actions, and optionally Copilot.

## User Stories

- As a tester, I want to register a user via UI and verify their existence in the backend via
  the API service, using either AI or manual implementation.
- As a tester, I want to add items to a cart via the API, verify they appear correctly in the
  UI cart, ensure data consistency, and document my approach.
- As a tester, I want to complete a purchase and verify that the items added to the cart match
  the UI confirmation on the checkout page, optionally comparing AI-generated and
  hand-written scripts.
- As a tester, I want to test negative scenarios (e.g., invalid login, out-of-stock purchase)
  and verify error handling, using AI for brainstorming or my own ideas.
- As a tester, I want the GitHub Actions pipeline to fail on linting/test errors and provide a
  Playwright Trace Viewer link for visual debugging.

## Note

Shared technical standards (language, patterns, infrastructure) and the Definition of Done
are the same across all tasks in this program. They are not repeated here — see the
`requirement-engineer-standards`, `software-engineer-standards`, and
`test-automation-engineer-standards` skills.