---
name: dev-code-quality
description: Apply Clean Code and SOLID principles while prioritizing maintainability, testability, and security during software implementation and code review.
---

# Clean Code & Software Quality

## Objective

Ensure that implemented code follows good software engineering practices.

The Developer must prioritize maintainability, testability, and security while avoiding unnecessary complexity.

Apply these principles according to the existing project architecture, programming language, framework, and approved design.

## 1. General Quality Priorities

Prioritize these attributes in every implementation:

1. Maintainability.
2. Testability.
3. Security.

Additional quality attributes, such as performance, scalability, reliability, and reusability, must only be considered when explicitly specified by the user or included in the approved task requirements.

Do not independently expand quality requirements or introduce unnecessary complexity.

## 2. Clean Code

Follow these practices:

### Naming

- Use meaningful and descriptive names.
- Follow language and framework naming conventions.
- Avoid ambiguous abbreviations.
- Names should communicate intent.

### Functions and Methods

- Keep functions focused on a clear responsibility.
- Avoid unnecessarily large methods.
- Avoid excessive parameters.
- Avoid hidden side effects.
- Keep business logic understandable.

### Classes and Modules

- Give each class or module a clear responsibility.
- Avoid classes that accumulate unrelated functionality.
- Keep dependencies explicit.
- Separate unrelated concerns.

### Readability

- Prefer straightforward code.
- Avoid unnecessary nesting.
- Avoid clever or unnecessarily complex expressions.
- Remove dead code when within the approved scope.
- Add comments when they explain important reasoning, not obvious operations.

### Error Handling

- Handle errors explicitly.
- Avoid silently swallowing exceptions.
- Provide useful error information.
- Do not expose sensitive information through error messages.
- Follow the application's established error-handling conventions.

## 3. SOLID Principles

Apply SOLID where it improves the design.

### Single Responsibility Principle (SRP)

A class or module should have one clear reason to change.

Avoid combining unrelated responsibilities.

### Open/Closed Principle (OCP)

Design components so they can be extended without unnecessarily modifying stable existing behavior.

Do not introduce abstraction without a justified need.

### Liskov Substitution Principle (LSP)

Subtypes should preserve the expected behavior of their parent abstractions.

Avoid inheritance structures that violate expected contracts.

### Interface Segregation Principle (ISP)

Prefer focused interfaces that expose only the functionality their consumers need.

Avoid unnecessarily large interfaces.

### Dependency Inversion Principle (DIP)

Depend on appropriate abstractions rather than tightly coupling high-level business logic to low-level implementation details.

Use dependency injection when it improves flexibility and testability.

## 4. Maintainability

Prioritize code that is easy to understand, modify, and extend.

Consider:

- Clear responsibilities.
- Low coupling.
- High cohesion.
- Consistent naming and organization.
- Explicit dependencies.
- Understandable business logic.
- Minimal duplication.
- Consistent project conventions.

Avoid premature abstraction and overengineering.

## 5. Testability

Write application code that can be tested independently.

Consider:

- Clear separation of business logic.
- Manageable dependencies.
- Predictable behavior.
- Explicit inputs and outputs.
- Isolated side effects where appropriate.
- Avoiding unnecessary global state.
- Appropriate dependency boundaries.

The Developer does not author tests. The Tester owns test implementation and execution.

## 6. Security

Follow secure coding practices appropriate to the task.

Consider:

- Input validation.
- Authorization and access control.
- Authentication boundaries.
- SQL injection prevention.
- Secure handling of sensitive information.
- Safe error responses.
- Secret management.
- Appropriate data exposure.
- Secure dependency usage.
- Avoiding insecure defaults.

Never hardcode credentials, tokens, or secrets.

Do not weaken existing security controls to simplify implementation.

If a security requirement is unclear or a significant vulnerability is discovered, raise it with the user.

## 7. Additional Quality Attributes

Only evaluate additional quality attributes when explicitly requested by the user or included in the approved task requirements.

Examples:

- Performance.
- Scalability.
- Reliability.
- Availability.
- Reusability.
- Portability.
- Observability.

Do not assume all attributes need equal consideration in every task.

## 8. Design Patterns

Use design patterns only when they solve an actual problem.

Examples:

- Factory.
- Strategy.
- Repository.
- Adapter.
- Observer.
- Command.
- Decorator.

Before introducing a pattern:

1. Identify the problem.
2. Explain why the pattern is suitable.
3. Evaluate its complexity.
4. Consider a simpler alternative.
5. Follow the approved design.

Do not force patterns into straightforward implementations.

## 9. Avoid Overengineering

- Prefer simple solutions.
- Do not create unnecessary interfaces.
- Do not introduce abstractions for hypothetical future needs.
- Do not add dependencies without justification.
- Do not refactor unrelated code.
- Do not implement functionality outside the task scope.

Follow the KISS principle and avoid premature optimization.

## 10. Code Quality Review

Before handing implementation to the Tester, review:

- Naming and readability.
- Function and class responsibilities.
- SOLID violations where relevant.
- Unnecessary coupling.
- Unnecessary duplication.
- Error handling.
- Security concerns.
- Maintainability.
- Testability.
- Compliance with approved design.

Report significant limitations rather than hiding them.

## Working Principle

Write readable code → Maintain clear responsibilities → Apply SOLID appropriately → Prioritize maintainability, testability, and security → Avoid overengineering → Review before handoff.
