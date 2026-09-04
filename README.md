# PR Review Toolkit — Setup Guide

This repository contains a GitHub Copilot agent and a set of skills that help you review your
own pull request **before** you open it for mentor review. It checks your code against the
task requirements, architecture standards, and the Definition of Done — so you can fix the
easy issues yourself first.

Current toolkit version: `1.0.0`. See [VERSION](VERSION) for the central version and
[CHANGELOG.md](CHANGELOG.md) for release history.

The toolkit lives in a separate repository. Follow the steps below **once** to bring it into
your own project repository.

## Prerequisites

- Git installed and working in your terminal
- Your project repository cloned locally
- GitHub Copilot enabled in VS Code

## Step 1 — Add the toolkit repository as a remote

Open a terminal inside your project repository and run:

```bash
git remote add mentor-toolkit https://github.com/k0libri/ta-copilot-review-toolkit.git
```

This adds the toolkit repository as a second remote, called `mentor-toolkit`. It does not
change your existing remote (`origin`) in any way.

## Step 2 — Fetch the toolkit branch

```bash
git fetch mentor-toolkit main
```

This downloads the branch from the toolkit repository, but does not merge anything into your
project yet.

## Step 3 — Copy the `.github` folder into your repository

```bash
git checkout mentor-toolkit/main -- .github
```

This command copies **only** the `.github` folder from the toolkit branch into your current
branch. It will not touch any of your other files or folders.

## Step 4 — Remove the temporary remote (optional cleanup)

```bash
git remote remove mentor-toolkit
```

You don't need the remote anymore once the files are copied. This step is optional but keeps
your repository clean.

## Step 5 — Review, commit, and push

```bash
git status
git add .github
git commit -m "Add PR review agent and skills"
git push
```

Check `git status` first, so you know exactly which files were added, before committing.

## How to use the toolkit

Once the files are in your repository, open GitHub Copilot Chat in VS Code and run:

```
@pr-review
```

The agent will ask which task you are working on (if it's not obvious), check your current
changes, and give you a review report grouped by **Critical**, **Should Fix**, and
**Suggestion**.

Run this **before** opening your PR. Fix what you can, then open the PR for mentor review.

For more details about the individual files, see `.github/README.md`.

## Getting updates later

If the toolkit is updated later (for example, a new task is added, or a checklist changes),
repeat Steps 1–5 to pull the latest version. Step 3 will overwrite the old `.github` folder
with the new one.