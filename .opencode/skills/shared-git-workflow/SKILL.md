---
name: shared-git-workflow
description: Shared Git version-control and GitHub collaboration rules for all development agents.
---

# Shared Git Workflow

## 1. Purpose

This skill defines the common rules for Git version control and GitHub collaboration.

It applies to:

- Project Manager
- Engineering Partner
- Developer
- Tester

The objective is to maintain a controlled, traceable, reviewable, and reversible development workflow.

## 2. Source of Truth

- **Git:** Source of truth for version-controlled application code and change history.
- **GitHub:** Source of truth for remote repositories, branches, pull requests, reviews, and code collaboration.
- **ClickUp:** Source of truth for requirements, tasks, acceptance criteria, and project progress.

Every implementation change should be traceable to its related ClickUp task.

## 3. Branch Strategy

The project uses the following main branches:

| Branch | Purpose |
|---|---|
| `main` | Production-ready code |
| `dev` | Integration and staging development |

Agents must never push directly to `main` or `dev`.

### Working branches

Use separate working branches for individual changes.

Supported branch categories:

- `feature/` - New functionality.
- `bugfix/` - Bug fixes.
- `hotfix/` - Urgent production fixes.
- `chore/` - Maintenance and tooling.
- `refactor/` - Code restructuring without intended behavior changes.

Examples:

- `feature/123-create-production-order`
- `bugfix/145-fix-stock-validation`
- `hotfix/167-fix-login-failure`
- `chore/180-update-dependencies`

Use the actual ClickUp task ID in the branch name when available.

### Branch rules

1. Start from the appropriate base branch.
2. Verify the current branch before making changes.
3. Keep each branch focused on one task or closely related change.
4. Do not implement unrelated work on the same branch.
5. Do not work directly on `main` or `dev`.
6. Do not change the base branch without user authorization.
7. Do not delete branches without user authorization.

If the correct base branch is unclear, ask the user.

## 4. Git Permissions and Approval

The following actions require explicit user approval:

| Action | Permission |
|---|---|
| Inspect repository and Git status | Allowed |
| Read Git history and diffs | Allowed |
| Create a working branch | Allowed only when authorized by the task or user |
| Modify application files | Subject to the agent's role and task approval |
| Stage changes | Explicit approval |
| Commit changes | Explicit approval |
| Push changes | Explicit approval |
| Open a pull request | Explicit approval |
| Merge a pull request | Explicit approval |
| Delete remote or local branches | Explicit approval |
| Deploy changes | Explicit approval |

### Important

- Commit permission does not imply push permission.
- Push permission does not imply permission to open a PR.
- PR creation does not imply merge permission.
- Merge permission does not imply deployment permission.
- Approval for one branch or task does not authorize actions on another.

When uncertain, stop and ask.

## 5. Commit Rules

Before committing:

1. Inspect the working tree.
2. Review the complete diff.
3. Check for unrelated changes.
4. Check for secrets, credentials, environment files, and sensitive data.
5. Verify that the changes belong to the intended task.
6. Obtain explicit commit approval.

Use clear, descriptive commit messages.

Recommended format:

`<type>: <short description>`

Examples:

- `feat: add production order creation`
- `fix: validate stock availability`
- `refactor: simplify order processing`
- `test: add production order scenarios`
- `chore: update dependencies`

Do not create commits without explicit approval.

## 6. Push Rules

Before pushing:

1. Verify the current branch.
2. Verify the remote repository and destination branch.
3. Review the commits being pushed.
4. Check that no protected branch is the destination.
5. Obtain explicit push approval.

### Mandatory restrictions

- Never push to `main`.
- Never push to `dev`.
- Push only the current authorized working branch.
- Never force-push unless the user explicitly authorizes it.
- Never overwrite remote history without explicit approval.
- Never push secrets or sensitive files.

If the current branch is `main` or `dev`, stop. Do not push.

## 7. Pull Request Rules

After an authorized push, create a pull request only when explicitly approved.

### PR destination

The normal integration target is:

`working branch → dev`

However, the target must be verified against the task and the user's instructions. Never assume a different target.

### Required PR information

Every PR must include:

1. **Title:** A concise description of the change.
2. **Feature or bug description:** What changed and why.
3. **Implementation summary:** The main changes made.
4. **Testing information:** Tests executed and their actual results.
5. **ClickUp task ID:** The exact related task ID.
6. **ClickUp task link:** A direct link to the related task.
7. **Known limitations:** Any remaining issues or risks.

### PR description template

#### Summary
Describe the feature, improvement, or bug fix.

#### Changes
- List the important changes.
- Explain relevant behavior changes.

#### Testing
- List tests actually executed.
- Include their results.
- Identify tests that were not executed.

#### ClickUp Reference
- Task ID: [ClickUp Task ID]
- Task: [ClickUp Task URL]

#### Notes
- Known limitations.
- Risks.
- Follow-up work, if applicable.

### PR rules

- Do not create a PR without explicit approval.
- Never create a PR targeting `main` unless explicitly authorized.
- Do not claim tests passed unless they were actually executed.
- Do not merge the PR.
- Do not deploy the PR.
- Keep the PR focused on its associated ClickUp task.

## 8. Synchronization and Conflict Handling

Before starting work, inspect the current branch and repository state.

When synchronizing:

- Fetch remote updates before relying on outdated branch information.
- Inspect incoming changes before integrating them.
- Prefer the project's established merge or rebase strategy.
- Do not rewrite shared branch history.
- Do not resolve ambiguous conflicts by guessing.
- Never discard user changes.

If conflicts occur:

1. Identify the conflicting files.
2. Understand both sides of the changes.
3. Explain the impact.
4. Resolve only when the intended behavior is clear and the agent is authorized.
5. Ask the user when a conflict requires a product or design decision.

## 9. Code Review and Pull Request Quality

Before requesting review:

- Inspect the full diff.
- Check for accidental changes.
- Check for debugging code and temporary files.
- Check for secrets and sensitive data.
- Verify consistency with approved requirements and design.
- Verify that the change does not introduce unrelated modifications.
- Include relevant test evidence.

Review comments should be addressed carefully.

Do not automatically accept suggestions that change requirements, security behavior, or approved architecture. Escalate such decisions to the user.

## 10. Agent-Specific Responsibilities

| Agent | Git/GitHub responsibility |
|---|---|
| Project Manager | Maintain task traceability and review project-level delivery status |
| Engineering Partner | Inspect code structure and provide technical recommendations; no unauthorized repository modifications |
| Developer | Implement approved application changes and prepare reviewable changes |
| Tester | Work with authorized test-related changes and report evidence; do not modify application implementation |

Each agent must respect its own skill boundaries.

## 11. Safety and Reversibility

- Keep changes small and reviewable.
- Avoid unrelated refactoring.
- Do not delete or overwrite user work.
- Do not use destructive Git commands without explicit approval.
- Do not bypass branch protections.
- Do not disable CI checks to make a PR pass.
- Preserve a clear history of changes.
- Prefer reversible changes where practical.

## 12. Final Rules

1. Never push to `main` or `dev`.
2. Commit only with explicit approval.
3. Push only with explicit approval.
4. Push only the authorized current working branch.
5. Open PRs only with explicit approval.
6. Every PR must reference its ClickUp task ID and direct link.
7. Never merge or deploy without explicit approval.
8. Never lose or overwrite user changes.
9. Never claim an operation succeeded unless it actually succeeded.

**The user remains the final authority over all Git and GitHub operations.**