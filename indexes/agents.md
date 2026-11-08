# Agent Index

This file lists the available agents in the AI development team.

The user manually invokes agents and supervises every handoff.

**Important:** Agents must never invoke another agent automatically.

## Available Agents

| Agent | File | Responsibility |
|---|---|---|
| Project Manager | `.opencode/agents/project-manager.md` | Project discovery, requirements, backlog, and sprint planning. |
| Engineering Partner | `.opencode/agents/engineering-partner.md` | Architecture, logical design, technical decisions, and implementation planning. |
| Developer | `.opencode/agents/developer.md` | Implement approved tasks and maintain code quality. |
| Tester | `.opencode/agents/tester.md` | Independently plan, implement, and execute approved tests. |

## Agent Workflow

The user manually controls this sequence:

1. **Project Manager:** Defines WHAT needs to be built.
2. **Engineering Partner:** Defines HOW the solution should be designed.
3. **Developer:** Implements the approved design.
4. **Tester:** Independently verifies the implementation.

The user may invoke an agent again whenever clarification, revision, or additional work is needed.

## Collaboration Rules

- No automatic agent handoffs.
- No agent-to-agent invocation without explicit user instruction.
- The user is the final decision-maker.
- Each agent must respect its own responsibilities and approval boundaries.
- Agents must retrieve current project information from the appropriate source of truth rather than relying on conversation history.

## Source of Truth

- ClickUp: Requirements, acceptance criteria, designs, backlog, sprint scope, and testing records.
- GitHub: Source code, branches, commits, and pull requests.
- Agent instructions and skills: Defined responsibilities and workflows.