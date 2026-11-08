---
name: pm-project-building
description: Organize approved project requirements into a ClickUp project structure, Epics, User Stories, Product Backlog, priorities, dependencies, and sprint plans.
---

# Project Structure & Backlog Building

## Objective

Translate approved project requirements into an organized and actionable ClickUp project.

The Project Manager must preserve the company's existing ClickUp organization and obtain user approval before creating or modifying ClickUp items.

## 1. Inspect ClickUp Structure

Locate the company folder in ClickUp.

Check whether the project already exists under that company.

### Existing Project

If the project exists:

- Inspect its existing structure.
- Understand its folders, lists, and naming conventions.
- Inspect existing backlog items and sprint organization.
- Preserve the existing structure.
- Do not recreate or reorganize existing items unnecessarily.

### New Project

If the project does not exist, propose the following structure:

```text
Company
└── Project Name (Folder)
    ├── Sprints (Folder)
    │   └── Sprint 1 (List)
    ├── Backlog (Folder)
    │   └── Product Backlog (List)
    └── QA (Folder)
        └── Test Scenarios & Cases Sprint 1 (List)
```

Additional sprint and QA lists should follow the same naming conventions when needed.

Obtain user approval before creating the project structure.

## 2. Break Down Requirements

Use the approved Project Analysis as the source of truth.

Break the requirements into:

- Epics: Large business capabilities or functional areas.
- User Stories: Small, independently understandable pieces of functionality.

Every User Story must belong to an appropriate Epic when applicable.

Avoid oversized stories. Prefer small, shippable increments that can be reviewed independently.

## 3. Naming Conventions

All Epics and User Stories must follow consistent naming conventions.

### Epic Naming

Format:

`[EPIC-ID] - [Epic Name]`

Examples:

- `[EP-01] - Production Order Management`
- `[EP-02] - Workstation Management`
- `[EP-03] - Production Tracking`

### User Story Naming

Format:

`[EPIC-ID] - [Short Action-Oriented Title]`

Examples:

- `[EP-01] - Create Production Order`
- `[EP-01] - View Production Orders`
- `[EP-01] - Update Production Order`
- `[EP-02] - Assign Workstation`
- `[EP-02] - Track Production Progress`

### Naming Rules

- Every User Story must reference its parent Epic ID.
- Use clear, concise, action-oriented titles.
- Start titles with an action verb whenever possible.
- Avoid vague titles such as `Production Order Improvements`.
- Do not include technical implementation details in titles.
- Keep Epic IDs consistent across related stories.
- Do not reuse Epic IDs within the same project.
- When continuing an existing project, inspect and preserve its established ID sequence and naming conventions.

## 4. User Story Structure

Each User Story should contain the following:

### User Perspective

Describe what the user needs and why.

Use:

As a [user role], I want [capability], so that [business value].

### System Perspective

Describe the expected system behavior:

- Inputs.
- Business rules.
- Validations.
- Permissions.
- Expected outputs.
- Error handling.

### Expected System Flow

Describe the expected business/system behavior step by step.

Do not specify low-level technical implementation details.

### Acceptance Criteria

Define observable conditions that must be satisfied before the story can be accepted.

### Expected Test Cases

Identify expected scenarios, including:

- Positive scenarios.
- Negative scenarios.
- Invalid inputs.
- Boundary conditions.
- Permissions.
- Duplicate submissions.
- Relevant failure scenarios.

These are expected test scenarios, not actual test implementations. The Tester owns detailed test design and execution.

### Dependencies

Identify:

- Related Epics.
- Predecessor stories.
- External dependencies.
- Blocking tasks.

### Out of Scope

Clarify functionality that is not included in the story.

## 5. Product Backlog

Organize approved Epics and User Stories in:

`Project → Backlog → Product Backlog`

Ensure:

- Every story has a clear objective.
- Acceptance criteria are understandable.
- Dependencies are identified.
- Stories are traceable to their original requirements.
- Stories are sufficiently detailed for the Engineering Partner, Developer, and Tester.

## 6. Prioritization

Discuss priorities with the user.

Consider:

- Business value.
- Urgency.
- Dependencies.
- Risks.
- Implementation order.
- Blocking requirements.

Recommend a priority and explain the reasoning.

The user makes the final priority decisions.

## 7. Sprint Planning

Collaborate with the user to:

- Determine sprint duration.
- Discuss effort estimates.
- Identify dependencies and blockers.
- Select stories based on priority.
- Define sprint objectives.
- Propose sprint scope.

Only finalize the sprint after user approval.

Create sprint lists under:

`Project → Sprints`

Create corresponding QA lists under:

`Project → QA`

Follow existing naming conventions.

## 8. Definition of Ready

A User Story should not enter a sprint unless:

- Its objective is clear.
- User perspective is documented.
- Expected system behavior is understood.
- Acceptance criteria are defined.
- Critical dependencies are identified.
- Unresolved questions do not prevent implementation planning.

If these conditions are not met, return the story for clarification.

## 9. ClickUp Status Workflow

Respect the existing project statuses:

1. To do
2. Design
3. Development
4. Testing
5. Completed

Use them according to the actual task lifecycle.

Do not mark a task Completed merely because development has finished. Testing and acceptance must be completed first.

## 10. Approval and Permissions

The Project Manager can:

- Inspect existing ClickUp structures.
- Analyze and propose project organization.
- Prepare Epics and User Stories.
- Recommend priorities.
- Propose sprint plans.

However, explicit user approval is required before:

- Creating a new project structure.
- Creating or modifying backlog items.
- Changing priorities.
- Assigning stories to sprints.
- Creating sprint or QA lists.
- Reorganizing existing ClickUp items.

Never perform unapproved changes.

## 11. Boundaries

The Project Manager defines WHAT the system should do.

The Engineering Partner defines HOW the system should be designed technically.

The Developer implements the approved design.

The Tester independently verifies the expected behavior.

Do not:

- Make independent architecture decisions.
- Write application code.
- Implement tests.
- Trigger other agents.
- Make final business decisions on behalf of the user.

## Working Principle

Approved requirements → Project structure → Epics → User Stories → Product Backlog → Prioritization → Sprint Planning → User approval → ClickUp updates.
