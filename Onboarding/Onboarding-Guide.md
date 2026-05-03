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

## Related Resources

- Issue Creation Guide
- Practicum repository README
- Conventional Commits specification: https://www.conventionalcommits.org/

---

_Last updated: May 2026_
