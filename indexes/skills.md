# Skill Index

This file lists the available skills and explains when each should be loaded.

Agents must load only the skills relevant to their current task.

Do not load every skill by default.

## Project Manager Skills

| Skill | Path | Purpose |
|---|---|---|
| Project Analysis | `.opencode/skills/pm-project-analysis/SKILL.md` | Discover requirements, analyze scope, identify ambiguities, and prepare clarification questions. |
| Project Building | `.opencode/skills/pm-project-building/SKILL.md` | Organize ClickUp, create Epics and User Stories, manage backlog, and plan sprints. |

## Engineering Partner Skills

| Skill | Path | Purpose |
|---|---|---|
| System Architecture | `.opencode/skills/ep-system-architecture/SKILL.md` | Design high-level system architecture and evaluate technical alternatives. |
| Logical Design | `.opencode/skills/ep-logical-design/SKILL.md` | Design feature-level logic, modules, classes, interfaces, and interactions. |
| Implementation Planning | `.opencode/skills/ep-implementation-planning/SKILL.md` | Prepare implementation-ready plans and Developer handoffs. |

## Developer Skills

| Skill | Path | Purpose |
|---|---|---|
| Implementation | `.opencode/skills/dev-implementation/SKILL.md` | Implement approved tasks, inspect code, work incrementally, and follow Git permissions. |
| Code Quality | `.opencode/skills/dev-code-quality/SKILL.md` | Apply Clean Code, SOLID, maintainability, testability, and security practices. |

## Tester Skills

| Skill | Path | Purpose |
|---|---|---|
| Test Planning | `.opencode/skills/test-planning/SKILL.md` | Analyze requirements and propose test scenarios and cases for user approval. |
| Test Execution | `.opencode/skills/test-execution/SKILL.md` | Implement and execute approved tests, report defects, and verify fixes. |

## Shared Skills

These skills provide common rules across multiple agents.

| Skill | Path | Purpose |
|---|---|---|
| Git Workflow | `.opencode/skills/shared-git-workflow/SKILL.md` | Shared branch, commit, push, PR, and Git permission rules. |
| ClickUp Rules | `.opencode/skills/shared-clickup-rules/SKILL.md` | Shared ClickUp structure, naming conventions, and approval rules. |
| Security | `.opencode/skills/shared-security/SKILL.md` | Common security requirements and safe engineering practices. |

## Skill Loading Rules

1. Read the agent's own instruction file first.
2. Identify the current task.
3. Load only the skills relevant to that task.
4. Load shared skills when their rules apply.
5. Avoid reloading skills already available in the current context.
6. Do not treat a skill as authorization to perform an action.
7. Follow the approval requirements defined in the skill and agent instructions.

## Important Boundaries

- Skills define workflows and standards, not additional permissions.
- Explicit user approval is still required for restricted actions.
- The user remains the final decision-maker.
- Agents must not invoke one another automatically.