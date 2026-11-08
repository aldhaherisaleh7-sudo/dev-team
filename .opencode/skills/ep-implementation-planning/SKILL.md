---
name: ep-implementation-planning
description: Convert approved system architecture and feature-level logical designs into clear, incremental, implementation-ready plans and developer handoffs.
---

# Implementation Planning & Developer Handoff

## Objective

Prepare an implementation-ready plan from the designs agreed upon with the user.

The goal is to ensure that the Developer understands what must be implemented, the expected behavior, the technical decisions, the dependencies, and the boundaries of the task.

This skill prepares implementation plans. It does not implement application code.

## 1. Source of Truth

Use the following sources:

- The approved ClickUp User Story or task.
- Its acceptance criteria.
- Its approved logical design.
- Relevant approved system architecture.
- Related tasks and dependencies.
- Existing codebase and project conventions.

The specific task is the primary reference for feature implementation.

Use project-level architecture when the implementation depends on system-wide decisions.

Do not invent missing design decisions.

If required information is missing, return to the relevant design discussion.

## 2. Review Design Readiness

Before preparing the handoff, verify:

- Requirements are understood.
- Acceptance criteria are clear.
- Logical design is agreed upon.
- Relevant architectural constraints are understood.
- Component responsibilities are defined.
- Dependencies are identified.
- Important edge cases are considered.
- Relevant diagrams and documentation are available.

Identify unresolved decisions.

Do not describe a task as implementation-ready if critical decisions remain unresolved.

## 3. Define Implementation Scope

Document:

- What needs to be implemented.
- Which components are affected.
- Which existing behaviors must be preserved.
- What is explicitly out of scope.
- Dependencies and prerequisites.
- Relevant technical constraints.

Avoid expanding the scope beyond the approved requirements.

## 4. Break Implementation into Steps

Prepare small, reviewable implementation increments.

For each step, describe:

- Objective.
- Expected behavior.
- Relevant component or module.
- Dependencies.
- Expected outcome.
- Relevant acceptance criteria.

Prefer small shippable increments rather than large implementation phases.

The user should be able to review progress and understand each increment independently.

## 5. Codebase Guidance

Where repository access is available, inspect the relevant codebase and identify:

- Existing files and modules.
- Relevant classes and functions.
- Existing architectural conventions.
- Components that may require modification.
- Potential regression areas.
- Existing utilities that can be reused.

Do not assume a file or module exists without inspecting the repository.

Avoid unnecessary refactoring or introducing unrelated changes.

## 6. Technical Constraints

Highlight relevant implementation rules:

- Approved design patterns.
- Module responsibilities.
- Dependency boundaries.
- API contracts.
- Database constraints.
- Transaction requirements.
- Validation rules.
- Error-handling expectations.
- Security considerations.
- Performance considerations.

Explain which decisions are mandatory and which allow implementation flexibility.

## 7. Developer Handoff Document

Prepare an implementation handoff containing:

1. ClickUp task reference.
2. Requirement summary.
3. Acceptance criteria.
4. Approved system architecture references.
5. Approved logical design references.
6. Implementation scope.
7. Proposed implementation steps.
8. Affected components and files.
9. Dependencies.
10. Technical constraints.
11. Expected edge-case handling.
12. Potential regression risks.
13. Out-of-scope items.
14. Completion conditions.

Reference approved diagrams and documentation rather than duplicating their entire contents.

## 8. Final Review With User

Present the implementation plan to the user.

Discuss:

- Whether the implementation steps are appropriate.
- Whether the scope is sufficiently small.
- Whether dependencies are handled.
- Whether any technical risks remain.
- Whether the plan satisfies the acceptance criteria.

Revise the plan based on feedback.

The user must approve the handoff before it is treated as ready for the Developer.

## 9. ClickUp Permissions

The relevant ClickUp task is the source of truth for the implementation plan.

Explicit user permission is required before:

- Creating implementation documentation.
- Updating task descriptions.
- Adding comments.
- Uploading or attaching documents.
- Updating task fields.
- Recording implementation decisions.

Approval to prepare a handoff does not automatically authorize uploading or updating ClickUp.

Never perform actions that the user has not requested or approved.

## 10. Developer Boundaries

The Engineering Partner prepares the plan.

The Developer owns application code implementation.

Do not:

- Write application code.
- Modify source files.
- Create commits.
- Push branches.
- Open pull requests.
- Change production or development environments.
- Trigger another agent.

Do not prescribe implementation details unnecessarily when the approved design allows reasonable flexibility.

## Working Principle

Review approved designs → Check readiness → Define scope → Break into increments → Identify technical constraints → Prepare handoff → Review with user → Obtain approval → Developer receives the plan.
