# Onboarding Guide for New Practicum Contributors

Welcome to the Seattle Colleges Application Development Practicum! This guide is designed to help new contributors get up to speed quickly with the team's workflow, repository structure, and contribution expectations.

## Purpose

This guide aims to:

- Reduce ramp-up time for new practicum students.
- Establish a shared understanding of how we work together.
- Provide a single reference point for common questions about contributing.

## Repository Structure

This repository contains version-controlled Markdown and other project files.

- [`belindas-closet/`](../belindas-closet/) contains documentation for Belinda's Closet.
- [`nsc-events/`](../nsc-events/) contains documentation for NSC Events.
- [`Onboarding/`](./) contains this guide.

The [published Practicum Wiki](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki) contains program-wide guidance, including [Issue Creation](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki/Issue-Creation).

## Picking Up an Issue

1. Navigate to the **Issues** tab in the repository.
2. Filter open issues using labels like `documentation`, `enhancement`, or `good first issue`.
3. Read the issue description carefully and check the existing comments.
4. If the issue is unassigned and you'd like to take it on:
   - Click **Assign yourself** in the right-hand panel, or
   - Leave a comment requesting assignment if you don't have permissions.
5. Confirm scope with a maintainer if anything is unclear before starting.

## Branch Naming Convention

Use the type categories in the Wiki's [Branch Creation](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki/Branch-Creation) guide. Keep your branch name short, lowercase, and dash-separated, using the form `<type>/<short-description>`.

- `feature/add-login-form` for a new feature
- `bug/fix-mobile-footer` for a bug fix
- `documentation/update-onboarding-guide` for a documentation change

Follow any additional naming rules in the repository where you are contributing.

## Pull Request Workflow

1. Create a branch from the base branch specified by the team, usually `main` or `develop`. For a follow-up that depends on an open PR, confirm the parent branch with the team and select it as the base.
2. Push your branch and open a [draft pull request](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki/Draft-and-Regular-PRs) early. Check that GitHub shows the intended base and compare branches.
3. Make small, focused commits with clear messages and push them to the same branch.
4. In the PR description, reference related work. Use `Refs #49` for the recurring weekly tracker so it stays open.
5. Mark the PR as **Ready for review** when your changes and verification are ready. Address feedback and re-request review when ready.

## Commit Message Guidelines

Follow the Conventional Commits convention used by the team:

- `feat:` — a new feature.
- `fix:` — a bug fix.
- `docs:` — documentation-only changes.
- `chore:` — maintenance tasks (dependencies, configs, etc.).
- `refactor:` — code changes that don't add features or fix bugs.

Example: `docs: add onboarding guide for new practicum contributors`

## Code Review Etiquette

Review at least two peer pull requests each week. See the Wiki's [PR Review Process](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki/PR-Review-Process) for the team workflow.

1. Read the description and linked issue. In **Files changed**, compare the diff with the acceptance criteria and identify what you need to verify.
2. Identify the PR head branch and latest commit in GitHub. For Markdown, open the rendered file on that branch and test the affected headings, links, and images. For local checks, use a clean checkout in the repository. With GitHub CLI, run the commands below and replace `123` with the PR number.

   ```bash
   git status --short
   gh pr checkout 123 --detach
   git rev-parse HEAD
   ```

   If `git status --short` lists changes, use a separate clean checkout before switching. Compare the printed commit with the PR's latest commit. If it differs, fetch the current PR and repeat the check.
3. Record the PR link, commit, steps, expected result, and what you observed. Capture your own screenshot or recording when the assignment calls for it. Include any checks you could not run.
4. Leave specific, constructive feedback in the PR. Use **Request changes** for blockers, **Comment** for suggestions, and **Approve** when the PR meets its acceptance criteria. Leave proposed edits as review suggestions so the author can apply them.

## Getting Help

If you get stuck:

1. Check the [published Practicum Wiki](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki) first.
2. Search closed issues and pull requests — your question may have been answered before.
3. Ask in the practicum team channel or tag a maintainer in the relevant issue.

## Setting Up Your Local Environment

Before contributing, set up your development environment so you can clone repositories and push commits cleanly.

### Required Tools

- **Git** — version control system. Download from https://git-scm.com/downloads.
- **A code editor** — Visual Studio Code is recommended (https://code.visualstudio.com/).
- **GitHub account** — make sure you've accepted the invitation to the SeattleColleges organization.

### Configure Git

After installing Git, set your identity so commits are properly attributed:

- Run `git config --global user.name "Your Name"`
- Run `git config --global user.email "your-github-email@example.com"`

Use the same email that's associated with your GitHub account so commits are linked to your profile.

### Authentication: SSH or HTTPS

GitHub supports two ways to authenticate when pushing code:

- **SSH** — generate an SSH key locally and add the public key to your GitHub account. More secure and convenient for daily work.
- **HTTPS with Personal Access Token (PAT)** — easier to set up initially, but the token must be regenerated periodically.

GitHub's official setup guides:

- SSH: https://docs.github.com/en/authentication/connecting-to-github-with-ssh
- PAT: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

### Verify Your Setup

Test that everything is working by running:

- `git clone https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki.git`
- `cd SeattleColleges-AD-Practicum-Wiki`
- `git status`

If `git status` runs without authentication errors, you're ready to start contributing.

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
- `git pull origin main` — update your current branch from `main` when that is your PR base. Substitute your PR's base branch when it differs.

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

## Frequently Asked Questions (FAQ)

### How many hours per week should I expect to spend on practicum work?

Approximately **3 hours per week** is the baseline expectation. This typically breaks down into about 1.5 hours on your assigned issue and 1–1.5 hours on PR reviews, weekly updates, and team communication.

### Do I need to be assigned to an issue before working on it?

Yes. Self-assign through GitHub if you have permission, or leave a comment asking a maintainer to assign you. This prevents duplicate work and keeps the issue tracker accurate.

### What do I do if my PR gets merge conflicts?

Update from the base shown on your pull request. For a PR targeting `main`, run `git pull origin main` from your own branch. Resolve the conflicts in your editor, commit the resolution, and push your branch. Ask in the team channel if you need help.

### How long should I wait for a review before nudging?

A reasonable cadence is **2–3 business days**. After that, leave a polite comment on the PR tagging the reviewers, or ask in the team channel. Reviews are part of the weekly expectations, so reviewers should be responsive.

### Can I work on issues in multiple repositories?

Yes, as long as you stay within the SeattleColleges practicum organization. Just make sure your weekly update links the correct repository, issue, and PR.

### What if I can't finish my issue in one week?

That's normal. Open a **draft PR** with whatever progress you have, link it to the issue, and note the remaining work in your weekly update. Incremental progress over multiple weeks is expected for larger issues.

## Common Git Troubleshooting

### "Authentication failed" when pushing

- Verify your remote URL: `git remote -v`. If it's HTTPS, regenerate your Personal Access Token. If it's SSH, confirm your SSH key is added to GitHub (`ssh -T git@github.com`).

### "Permission denied (publickey)"

- Your SSH key is missing or not added to your GitHub account. Follow GitHub's SSH setup guide and re-test the connection.

### Your branch is behind its PR base

- Pull the latest changes from the base listed on the PR. For a PR targeting `main`, run `git pull origin main` from your own branch. This may create a merge commit if the branches have diverged.

### "Merge conflict in <file>"

- Open the conflicted file in your editor. You'll see markers like `<<<<<<<`, `=======`, and `>>>>>>>` showing the two versions. Edit to keep the correct content, remove the markers, then run `git add <file>` and `git commit` to finalize.

### Accidentally committed to `main` locally

- Create a new branch from your current state: `git checkout -b feature/your-branch`. Then reset `main` to match origin: `git checkout main && git reset --hard origin/main`. Your commits are preserved on the new branch.

### Want to discard local changes to a file

- Run `git restore <file>` to revert it to the last committed version. If the file is already staged, run `git restore --staged <file>` first.

### Lost commits after a `reset --hard`

- Run `git reflog` to see your recent HEAD history. Find the commit hash you want to restore, then run `git checkout <commit-hash>` or `git reset --hard <commit-hash>`.

## Communication Channels and Team Etiquette

Clear communication keeps the practicum running smoothly, especially since the team works asynchronously across different schedules.

### Where to Communicate

- **GitHub Issues** — for proposing, discussing, and tracking work. Use issue comments to ask scope questions before starting.
- **Pull Request comments** — for code-specific discussion tied to a change. Keep technical back-and-forth here so it stays attached to the relevant diff.
- **Team channel (Slack/Discord)** — for quick questions, coordination, and unblocking. Use threads to keep topics organized.

### Asynchronous Communication Etiquette

- **Default to writing things down.** A comment on the issue or PR is more useful than a verbal hallway conversation, because it's searchable and visible to the whole team.
- **Provide context.** When asking for help, include what you tried, the exact error message, and a link to the relevant issue or PR. This reduces back-and-forth.
- **Tag intentionally.** Use `@mentions` when you need a specific person's input, but avoid tagging everyone for routine updates.

### Response Time Expectations

- Aim to respond to review requests and direct questions within **2–3 business days**.
- If you'll be unavailable for an extended period, leave a note on your active issues/PRs so others can plan around it.

### Escalating a Blocker

1. Re-check the documentation and existing issues/PRs first.
2. Ask in the team channel with full context.
3. If still blocked after a reasonable wait, tag the relevant maintainer directly on the issue or PR.

### Giving and Receiving Feedback

- Assume good intent — everyone is here to learn.
- Frame feedback around the work, not the person.
- When receiving feedback, acknowledge it even if you plan to address it later, so the reviewer knows it was seen.

## Related Resources

- [Issue Creation guide](https://github.com/SeattleColleges/SeattleColleges-AD-Practicum-Wiki/wiki/Issue-Creation)
- [Practicum repository README](../README.md)
- [Conventional Commits specification](https://www.conventionalcommits.org/)

---

_Last updated: May 2026_
