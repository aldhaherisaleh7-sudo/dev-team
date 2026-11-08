---
name: test-planning
description: Analyze approved requirements and technical designs, propose test scenarios and cases, and obtain user approval before test implementation or execution.
---

# Test Planning

## Objective

Translate approved requirements into a structured testing plan.

The Tester independently identifies what needs to be verified, how it should be verified, and what conditions determine whether the implementation passes or fails.

The user must review and approve all proposed test cases before any test implementation or execution begins.

## 1. Source of Truth

Before planning tests, retrieve and review:

- Relevant ClickUp User Story.
- User perspective and system perspective.
- Expected system flow.
- Acceptance criteria.
- Business rules and validations.
- Permissions and authorization requirements.
- Dependencies.
- Approved logical design.
- Relevant system architecture.
- Existing test scenarios and cases.
- Relevant existing tests in the codebase.

Use approved requirements as the primary basis for testing.

Do not treat Developer explanations or implementation decisions as replacements for approved requirements.

If requirements are ambiguous, incomplete, or contradictory, raise clarification questions to the user.

## 2. Independent Analysis

Analyze requirements independently from the Developer's implementation.

Identify:

- Expected behavior.
- Valid inputs.
- Invalid inputs.
- Boundary conditions.
- Business rule violations.
- Permission restrictions.
- Expected errors.
- Alternative execution paths.
- Integration dependencies.
- Potential regression areas.

Do not assume that the Developer has considered every possible scenario.

## 3. Test Strategy

Choose appropriate testing levels according to the task.

Examples:

- Unit testing.
- Integration testing.
- API testing.
- Functional testing.
- End-to-end testing.
- Regression testing.
- Security testing.

Do not introduce unnecessary testing layers.

Choose the smallest effective testing strategy that provides sufficient confidence in the implementation.

## 4. Test Scenarios and Cases

For each User Story, derive proposed test scenarios from its acceptance criteria and expected system behavior.

Each proposed test case should include:

- Test Case ID.
- Related User Story ID.
- Scenario title.
- Objective.
- Preconditions.
- Test data.
- Execution steps.
- Expected result.
- Priority.
- Relevant acceptance criterion.

Include relevant cases covering:

### Positive Testing

Verify that valid operations produce the expected results.

### Negative Testing

Verify that invalid operations are rejected correctly.

### Boundary Testing

Verify behavior at important limits and boundary conditions.

### Permission Testing

Verify that users can only perform authorized operations.

### Error Handling

Verify that errors are handled correctly without exposing sensitive information.

### Regression Scenarios

Identify existing functionality that could be affected by the changes.

## 5. Mandatory Test Case Approval Gate

This is a mandatory stage. It must never be skipped.

### Step 1: Present Proposed Test Cases

Before writing or modifying any test code, present the complete proposed test cases to the user.

Organize them by User Story and scenario category.

Include all required test case details so the user can understand what each case verifies.

### Step 2: Discuss and Refine

Allow the user to:

- Approve individual test cases.
- Modify existing test cases.
- Remove unnecessary test cases.
- Add new test cases.
- Request additional edge cases.
- Change priorities.
- Clarify expected behavior.

Revise the test plan according to the user's feedback.

Do not interpret silence or general discussion as approval.

### Step 3: Obtain Explicit Approval

Ask the user to explicitly approve the final test case set.

Record which test cases are approved.

If the user approves only part of the test plan, only those approved cases may proceed.

### Step 4: Preserve the Approved Scope

After approval:

- Do not silently modify approved test cases.
- Do not remove approved scenarios.
- Do not introduce additional test cases without user approval.
- If new scenarios become necessary, present them for approval first.

**Important:** Approval of test scenarios and cases does not automatically authorize writing test code or executing tests. Those actions require their own approval gate under `test-execution`.

## 6. Coverage and Traceability

Every acceptance criterion must have corresponding test coverage.

Maintain traceability:

User Story → Acceptance Criteria → Test Scenarios → Test Cases → Execution Results.

Identify acceptance criteria without test coverage.

Identify test cases that are not connected to an approved requirement and explain why they are necessary before proposing them.

## 7. Test Data

Define appropriate test data.

Consider:

- Valid data.
- Invalid data.
- Missing data.
- Boundary values.
- Duplicate data.
- Related records.
- Unauthorized users.
- Relevant system states.

Use isolated or controlled test data.

Never use production data or modify production records without explicit authorization.

Do not expose credentials, tokens, or sensitive information in test data.

## 8. ClickUp QA Management

Use the existing project structure:

`CAF → MAINTENANCE SYSTEM → QA → Test Scenarios & Cases [Sprint Number]`

Preserve existing conventions and records.

Organize scenarios and cases by their related User Stories.

Before creating or modifying ClickUp records, obtain explicit user approval.

Do not create duplicate test cases.

## 9. Planning Deliverable

Present:

1. Testing objective.
2. Scope of testing.
3. Testing levels and approach.
4. Proposed test scenarios.
5. Detailed proposed test cases.
6. Acceptance criteria coverage.
7. Test data requirements.
8. Dependencies and environment requirements.
9. Risks and open questions.
10. Approval status.

Clearly distinguish between proposed and approved test cases.

## 10. Boundaries

- Do not modify application code.
- Do not write or modify test code during planning.
- Do not execute tests before the required approvals.
- Do not change approved requirements.
- Do not invent expected behavior.
- Do not approve your own assumptions.
- Do not skip negative or boundary scenarios without justification.
- Do not execute tests against production without explicit authorization.
- Do not trigger other agents.
- Do not modify ClickUp without explicit approval.

## Working Principle

Review requirements → Analyze expected behavior → Identify test conditions → Propose test scenarios → Present test cases → Discuss and refine → Obtain explicit user approval → Hand off the approved test plan.
