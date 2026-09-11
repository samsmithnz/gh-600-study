# GH-600 Study Guide

Use this page as a practical study plan for the GH-600 exam and the GH-600T00 Microsoft Learn course, **Developing in Agentic AI Systems**.

Official references:

- [Study guide for Exam GH-600](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-600)
- [Course GH-600T00: Developing in Agentic AI Systems](https://learn.microsoft.com/en-us/training/courses/gh-600t00)

> Microsoft can update exam objectives over time. Before scheduling the exam, compare this guide with the official study guide and adjust your study plan to the latest skills outline.

## Exam focus

GH-600 is focused on building, configuring, operating, and governing agentic AI systems in software delivery workflows. Expect questions about how agents use tools, interact with development environments, preserve useful context, coordinate with other agents, and remain auditable and safe.

A strong candidate should be able to:

- Explain where agentic AI fits in the software development lifecycle.
- Configure tools, environments, and permissions that agents need to complete tasks.
- Manage agent memory, state, and context across sessions.
- Evaluate agent outputs and improve instructions, tools, and workflows.
- Coordinate multiple agents without creating conflicting or unsafe changes.
- Apply guardrails, accountability, and human review to agentic workflows.

## Skills outline and study priorities

### 1. Prepare agent architecture and SDLC processes

Study goals:

- Describe common agent roles in planning, implementation, review, testing, documentation, and operations.
- Decide which tasks are appropriate for an agent and which require human ownership.
- Define clear inputs, outputs, acceptance criteria, escalation paths, and review checkpoints.
- Map agent activity into repository workflows such as issues, pull requests, checks, approvals, and audit trails.

Practice tasks:

- Convert a vague issue into an agent-ready task with explicit scope, constraints, and done criteria.
- Design a pull request workflow that requires automated checks and human review before merge.
- Identify points where a human should approve access, changes, deployments, or destructive actions.

### 2. Implement tool use and environment interaction

Study goals:

- Explain how agents interact with files, shells, build systems, test runners, package managers, APIs, and external tools.
- Understand Model Context Protocol (MCP) concepts: servers expose tools/resources, clients call them, and permissions constrain access.
- Configure an agent environment so required dependencies, credentials, and tools are available without over-permissioning.
- Recognize failure modes such as missing dependencies, stale workspace state, flaky tools, rate limits, and insufficient permissions.
- Apply least privilege when granting repository, workflow, package, cloud, or third-party access.

Practice tasks:

- Given a repository, list the exact commands an agent should use to install, build, lint, and test it.
- Draft safe tool permissions for a coding agent that can edit code but cannot deploy production resources.
- Troubleshoot a failed agent run caused by a missing dependency or blocked tool permission.

### 3. Manage memory, state, and execution

Study goals:

- Distinguish short-term context, persistent memory, repository facts, user preferences, and external state.
- Decide what information should be remembered, what should remain session-local, and what should never be stored.
- Explain context-window limits, memory drift, stale assumptions, and the need to verify important facts against source files.
- Track long-running work through plans, checkpoints, commits, pull requests, and issue updates.

Practice tasks:

- Review sample memories and decide which are useful, duplicate, outdated, sensitive, or too task-specific.
- Create a recovery plan for an interrupted agent session that preserves completed work and next steps.
- Identify repository facts that should be cited from files rather than inferred from prior conversation.

### 4. Perform evaluation, error analysis, and tuning

Study goals:

- Evaluate agent output using acceptance criteria, tests, linters, code review, security scanning, and manual verification.
- Interpret failure logs, workflow artifacts, test output, review comments, and audit events.
- Improve outcomes by refining prompts, instructions, tool availability, environment setup, examples, and validation gates.
- Recognize hallucinations, overbroad changes, missed edge cases, and unsafe assumptions.

Practice tasks:

- Given a failing CI log, identify the root cause and the smallest next debugging step.
- Compare an agent's proposed fix with the original requirement and flag unrelated changes.
- Write a short evaluation checklist for a pull request produced by an agent.

### 5. Orchestrate multi-agent coordination

Study goals:

- Know when to use specialized agents for exploration, implementation, review, testing, research, or security analysis.
- Coordinate work so agents do not overwrite each other, duplicate effort, or act on stale context.
- Define ownership boundaries, handoff points, shared artifacts, and conflict-resolution steps.
- Use independent validation agents or reviews to catch logic, quality, and security issues.

Practice tasks:

- Split a large issue into independent agent tasks with clear file or responsibility boundaries.
- Design a handoff summary that includes completed work, decisions, risks, and remaining validation.
- Identify race conditions that can occur when two agents edit the same branch or workflow.

### 6. Implement guardrails and accountability

Study goals:

- Apply security and governance controls such as least privilege, branch protection, required reviews, required checks, and environment approvals.
- Understand how audit logs, commit history, pull request reviews, and workflow logs support accountability.
- Prevent risky behavior such as committing secrets, bypassing review, changing unrelated files, or deploying without approval.
- Balance automation with human-in-the-loop review for sensitive code, data, infrastructure, and production operations.

Practice tasks:

- Review a proposed agent permission set and remove unnecessary capabilities.
- Define a policy for when an agent may create, modify, or close issues and pull requests.
- Explain how to investigate who or what made a repository change.

## Suggested study path

1. **Read the official GH-600 study guide.** Capture each skill area and highlight any topic you cannot explain from memory.
2. **Skim GH-600T00.** Use the course outline to identify the main scenarios Microsoft expects you to practice.
3. **Practice in a real repository.** Work through issue creation, agent instructions, environment setup, pull requests, validation, and review.
4. **Focus on tool use and safety.** Be comfortable reasoning about permissions, MCP tools, environment setup, logs, and guardrails.
5. **Create flashcards.** Prioritize terms such as agent, tool, MCP server, context, memory, state, evaluation, guardrail, audit log, and least privilege.
6. **Review failure scenarios.** Practice diagnosing bad instructions, missing tools, unsafe permissions, stale memory, and conflicting agent edits.
7. **Take a mock pass.** For each exam domain, answer: what is the goal, what can go wrong, how do you validate success, and what controls reduce risk?

## Quick reference checklist

Before the exam, make sure you can confidently answer these prompts:

- What makes a task suitable or unsuitable for an agent?
- How should an agent be instructed to make minimal, reviewable changes?
- What tools does an agent need, and what permissions should it not have?
- How do MCP servers expand an agent's capabilities?
- What should be stored in memory, and what should be kept out?
- How do you evaluate and tune an agent after a failed or low-quality result?
- How do multiple agents coordinate without conflicting changes?
- Which GitHub controls provide review, traceability, and accountability?
- How do you detect and prevent secrets, unsafe code, and unauthorized actions?

## Hands-on labs to build confidence

Use a disposable repository or sandbox environment for these exercises:

- Configure a repository with clear agent instructions and a validation checklist.
- Ask an agent to implement a small issue, then review whether it stayed within scope.
- Add a simple CI check and require it before merging.
- Simulate a failed build or test and practice reading logs to identify the root cause.
- Draft an MCP tool access policy for a read-only research agent and a code-editing agent.
- Review an agent-created pull request for unrelated changes, missing tests, and unsafe permissions.
- Create an incident-style timeline from issue comments, commits, workflow logs, and review events.

## Final review strategy

Spend the final study session on scenario questions rather than memorization. For each scenario, identify:

- The agent's goal and allowed scope.
- The tools and permissions required.
- The human review or approval point.
- The validation evidence needed to trust the result.
- The audit trail that proves what happened.
