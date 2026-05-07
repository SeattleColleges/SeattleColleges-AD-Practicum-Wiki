# Onboarding Guide for New Practicum Contributors

Welcome to the Seattle Colleges Application Development Practicum! This guide is designed to help new contributors get up to speed quickly with the team's workflow, repository structure, and contribution expectations.

## Purpose

This guide aims to:

- Reduce ramp-up time for new practicum students.
- Establish a shared understanding of how we work together.
- Provide a single reference point for common questions about contributing.

## Repository Structure

The Practicum Wiki repository is organized into the following key areas:

- **`belindas-closet/`** — Documentation related to the Belinda's Closet project.
- **`nsc-events/`** — Documentation for the NSC Events project.
- **`Issue-Creation/`** — Guidelines for creating well-formed issues.
- **`Onboarding/`** — This guide and related onboarding materials.

## Picking Up an Issue

1. Navigate to the **Issues** tab in the repository.
2. Filter open issues using labels like `documentation`, `enhancement`, or `good first issue`.
3. Read the issue description carefully and check the existing comments.
4. If the issue is unassigned and you'd like to take it on:
   - Click **Assign yourself** in the right-hand panel, or
   - Leave a comment requesting assignment if you don't have permissions.
5. Confirm scope with a maintainer if anything is unclear before starting.

## Branch Naming Convention

Use descriptive branch names that link to the issue you're working on:

- `feature/issue-<number>-<short-description>` for new features
- `fix/issue-<number>-<short-description>` for bug fixes
- `docs/issue-<number>-<short-description>` for documentation changes

Example: `feature/issue-49-onboarding-guide`

## Pull Request Workflow

1. Create a branch from `main` linked to your issue.
2. Make small, focused commits with clear messages.
3. Open a **draft pull request** early to share progress with the team.
4. Reference the related issue in the PR description using `Closes #<issue-number>`.
5. Mark the PR as **Ready for review** once your work is complete.
6. Address review feedback promptly and re-request review when ready.

## Commit Message Guidelines

Follow the Conventional Commits convention used by the team:

- `feat:` — a new feature.
- `fix:` — a bug fix.
- `docs:` — documentation-only changes.
- `chore:` — maintenance tasks (dependencies, configs, etc.).
- `refactor:` — code changes that don't add features or fix bugs.

Example: `docs: add onboarding guide for new practicum contributors`

## Code Review Etiquette

- Be respectful and constructive — focus on the code, not the person.
- Use **Request changes** for blocking issues, **Comment** for suggestions, and **Approve** when satisfied.
- Do not push commits directly to another contributor's branch — leave feedback so they can address it themselves.
- Aim to review at least two open pull requests per week as part of practicum expectations.

## Getting Help

If you get stuck:

1. Check existing documentation in this Wiki first.
2. Search closed issues and pull requests — your question may have been answered before.
3. Ask in the practicum team channel or tag a maintainer in the relevant issue.

## Common Git Commands Cheatsheet

A quick reference for the Git commands most commonly used during practicum work:

### Setup and Cloning

- `git clone <repo-url>` — clone a repository to your local machine.
- `git config --global user.name "Your Name"` — set your Git username.
- `git config --global user.email "you@example.com"` — set your Git email.

### Working with Branches

- `git branch` — list all local branches.
- `git checkout -b <branch-name>` — create and switch to a new branch.
- `git checkout <branch-name>` — switch to an existing branch.
- `git fetch origin` — download latest refs from the remote without merging.
- `git pull origin main` — pull the latest changes from `main` into your current branch.

### Staging and Committing

- `git status` — see which files are modified or staged.
- `git add <file>` — stage a specific file for commit.
- `git add .` — stage all modified files.
- `git commit -m "feat: short message"` — commit staged changes with a message.
- `git push -u origin <branch-name>` — push your branch to the remote for the first time.
- `git push` — push subsequent commits to the same branch.

### Reviewing and Undoing

- `git log --oneline` — see a compact commit history.
- `git diff` — see unstaged changes.
- `git restore <file>` — discard local changes to a file.
- `git reset HEAD <file>` — unstage a file without losing changes.

## Weekly Development Update Expectations

Each practicum contributor is expected to submit a weekly development update covering the following:

- **Total hours dedicated** — approximately 3 hours per week is expected.
- **Task breakdown** — list each task or activity along with hours spent.
- **Assigned issue progress** — link to the issue and summarize current status, key learnings, and any blockers.
- **Branch link** — the branch where work is being done for the assigned issue.
- **Draft PR / PR progress** — link to active pull requests with summary of progress, learnings, and next steps.
- **Wiki documentation check** — confirm whether code changes affected existing Wiki content and update accordingly.
- **Pull request reviews (minimum 2 per week)** — link to each reviewed PR, summary of feedback, and learnings from the review process.

Submitting weekly updates consistently is mandatory and contributes to your practicum grade.

## Related Resources

- Issue Creation Guide
- Practicum repository README
- Conventional Commits specification: https://www.conventionalcommits.org/

---

_Last updated: May 2026_
