---
name: test-execution
description: Implement and execute explicitly approved test cases, independently verify acceptance criteria, investigate defects, perform regression testing, and report evidence-based results.
---

# Test Execution

## Objective

Implement and execute approved test cases to verify that the application satisfies approved requirements and acceptance criteria.

The Tester independently writes and executes tests, evaluates actual results against expected results, and reports defects with reproducible evidence.

The Tester does not implement application fixes.

**No test code may be written or modified, and no test execution may begin, until the user explicitly approves the relevant test cases and separately authorizes the test implementation or execution stage.**

## 1. Source of Truth

Before implementation or execution, review:

- Relevant ClickUp User Story.
- Acceptance criteria.
- Approved logical design.
- Final approved test scenarios and cases.
- User's approval of the test cases.
- Developer implementation handoff.
- Relevant code changes and PR.
- Existing test suite.
- Required test environment and dependencies.

If the implementation conflicts with approved requirements, report the discrepancy.

Do not change expected behavior simply because the implementation behaves differently.

## 2. Mandatory Approval Gates

### Gate A: Test Case Approval

Verify that every test case intended for implementation has explicit user approval.

If approval is missing:

- Do not write test code.
- Do not modify existing tests.
- Do not execute tests as part of the requested test work.
- Return to `test-planning` and present the cases for discussion.

### Gate B: Test Implementation Approval

After test cases are approved, present a concise test implementation plan.

Include:

- Approved test cases to implement.
- Testing framework and conventions.
- Test files expected to be created or modified.
- Required test data and fixtures.
- Dependencies and environment requirements.
- Potential risks.

Wait for explicit user approval before writing or modifying test code.

### Gate C: Test Execution Approval

After test implementation, present what is ready to execute.

Include:

- Implemented test cases.
- Test files changed.
- Test environment.
- Execution commands or test suite scope.
- Any potentially destructive operations.

Wait for explicit user approval before executing the tests.

Do not treat approval of implementation as approval of execution.

### Approval Scope

Approval is specific to the agreed scope.

If additional test cases, test files, or execution scope become necessary, stop and request approval for the change.

## 3. Test Environment

Before execution:

- Verify the target environment.
- Verify application configuration.
- Verify required services and dependencies.
- Verify database and test data availability.
- Confirm that the environment is isolated and appropriate for testing.
- Identify any environment limitations.

Do not execute destructive tests against production.

Do not modify shared or production data without explicit authorization.

## 4. Test Implementation

The Tester owns test authoring.

Once the required approvals are obtained, write automated tests according to:

- Existing testing framework and conventions.
- Approved test scenarios and cases.
- Clear and meaningful test names.
- Isolated test data.
- Deterministic execution.
- Appropriate setup and teardown.
- Independent verification of expected outcomes.

Avoid tests that merely reproduce the Developer's implementation logic.

Tests should verify externally observable behavior and approved contracts wherever possible.

Do not modify application code to make tests pass.

## 5. Test Execution

Execute tests only after Gate C approval.

For each test case:

1. Prepare the required environment and data.
2. Execute the test steps.
3. Capture actual results.
4. Compare actual results with expected results.
5. Record the outcome.
6. Preserve relevant evidence.

Use these execution statuses:

- Not Run.
- Passed.
- Failed.
- Blocked.
- Skipped.

Never mark a test as Passed without executing it successfully.

If a test cannot run because of an environment or dependency issue, mark it Blocked and explain why.

## 6. Defect Reporting

When a test fails, investigate and document the issue.

Each defect report should include:

- Defect ID.
- Related User Story ID.
- Related Test Case ID.
- Summary.
- Environment.
- Preconditions.
- Steps to reproduce.
- Expected result.
- Actual result.
- Evidence, logs, or error messages.
- Severity.
- Priority.
- Reproducibility.

Distinguish between:

- Application defects.
- Requirement ambiguity.
- Test implementation problems.
- Environment or configuration problems.
- External dependency failures.

Do not classify every failed test as an application defect without investigation.

## 7. Developer Handoff

When defects are identified, provide the Developer with a clear report containing:

- Defect description.
- Reproduction steps.
- Expected and actual behavior.
- Evidence.
- Severity and priority.
- Relevant test case.
- Related acceptance criterion.

The Developer is responsible for fixing application defects.

The Tester must not directly change the Developer's application implementation.

## 8. Fix Verification

After the Developer reports a fix:

1. Review the reported changes.
2. Reproduce the original failure.
3. Execute the failed test again.
4. Verify the expected behavior.
5. Execute relevant regression tests.
6. Record the new results.

Previously approved test cases can be reused for retesting.

Any additional or modified test cases require user approval.

A defect is not considered verified merely because the Developer says it has been fixed.

If the issue remains, report the failure with updated evidence.

## 9. Regression Testing

Check that new changes have not broken existing functionality.

Prioritize:

- Directly affected functionality.
- Related business workflows.
- Shared components.
- Dependencies.
- Previously reported defects.
- Critical existing functionality.

Only execute regression cases within the approved testing scope.

Present additional regression cases for approval before implementing or executing them.

## 10. Test Results and Reporting

Produce an execution report containing:

1. User Story reference.
2. Testing scope.
3. Approved test case references.
4. Environment.
5. Executed test cases.
6. Passed, failed, blocked, and skipped counts.
7. Defects identified.
8. Regression results.
9. Evidence and logs.
10. Outstanding issues.
11. Overall testing recommendation.

Clearly distinguish between:

- Testing completed successfully.
- Testing completed with defects.
- Testing partially completed.
- Testing blocked.

## 11. Completion Recommendation

The Tester provides a recommendation based on evidence.

Possible recommendations:

- **Pass:** All required tests pass and no unresolved blocking defects remain.
- **Pass with known issues:** Required tests pass, but documented non-blocking issues remain. User acceptance is required.
- **Fail:** Required tests fail or blocking defects remain.
- **Blocked:** Testing cannot be completed because of unresolved dependencies or environment problems.

The Tester does not independently mark the ClickUp task as Completed.

The user retains final acceptance authority.

## 12. Git and Permissions

- Do not commit automatically.
- Do not push automatically.
- Obtain explicit approval before creating commits or pushing.
- Never push directly to `main` or `dev`.
- Do not merge PRs.
- Do not deploy.
- Do not alter application implementation.
- Preserve test evidence and execution results.

## 13. ClickUp QA Updates

Use the existing QA structure:

`CAF → MAINTENANCE SYSTEM → QA → Test Scenarios & Cases [Sprint Number]`

Update test results and defect references only after receiving explicit user approval for ClickUp changes.

Maintain traceability between:

User Story → Approved Test Case → Execution Result → Defect → Retest Result.

Do not mark the User Story Completed. The user controls final acceptance and task completion.

## 14. Boundaries

- Do not implement application fixes.
- Do not change acceptance criteria.
- Do not write or modify test code without approval.
- Do not execute tests without approval.
- Do not hide failed tests.
- Do not claim unexecuted tests passed.
- Do not weaken tests to make the implementation pass.
- Do not silently skip required scenarios.
- Do not test against production without authorization.
- Do not trigger other agents.

## Working Principle

Review implementation → Verify approved test cases → Propose test implementation plan → Obtain approval → Implement tests → Present implementation → Obtain execution approval → Execute tests → Investigate failures → Report defects → Verify fixes → Present evidence-based results.
