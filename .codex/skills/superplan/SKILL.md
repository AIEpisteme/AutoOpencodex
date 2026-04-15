---
name: superplan
description: Produce a comprehensive end-to-end software delivery plan for product, platform, or infrastructure work. Use when Codex needs to turn a request into a full execution package covering planning, requirements, design, implementation sequencing, debugging and root-cause analysis, testing, integration, deployment, rollback, production verification, and outcome documentation. Prefer this skill for multi-step, risky, cross-functional, production-facing, or ambiguous engineering work where the user wants a rigorous plan before broad implementation.
---

# Super Plan

Build a delivery plan that another strong engineer could execute without guessing at the missing parts.

Keep the plan grounded in the actual repository, system constraints, and user objective. Do not produce generic SDLC boilerplate detached from the codebase or operating environment.

## Quick Start

1. Inspect the repo, relevant files, interfaces, and existing delivery constraints before planning in detail.
2. Restate the objective, scope, constraints, assumptions, and success criteria in concrete terms.
3. Produce the delivery package in the order below:
   - Problem framing
   - Requirements
   - Solution design
   - Implementation plan
   - Debugging and root-cause analysis
   - Validation strategy
   - Integration and release plan
   - Deployment and rollback plan
   - Production verification
   - Outcome documentation and follow-up
4. State unknowns explicitly and separate confirmed facts from assumptions.
5. Never claim a deployment, validation step, or production check was completed unless it was actually performed.

## Planning Rules

- Optimize for correctness, safety, maintainability, observability, reversibility, and business impact.
- Prefer small, testable increments over large risky changes.
- Fix root causes rather than patching symptoms.
- Make every requirement testable.
- Tie design decisions to concrete risks, dependencies, or operational constraints.
- Include rollback thinking for any production-facing change.
- Call out anything that blocks safe execution.

## Workflow

### 1. Problem Framing

Establish:

- Business or product objective
- User persona, system actor, or owning team
- In-scope and out-of-scope work
- Dependencies, external systems, and environments
- Constraints such as deadlines, compliance, performance, migration limits, and staffing assumptions
- Measurable success criteria

Output:

- Problem statement
- Goals
- Non-goals
- Constraints
- Assumptions
- Risks and unknowns

### 2. Requirements

Define precise, testable requirements:

- Functional requirements
- Non-functional requirements
- Interface or API expectations
- Data and schema expectations
- Error-handling expectations
- Security and privacy requirements
- Performance and reliability targets
- Observability requirements
- Acceptance criteria

For each major requirement, specify how it will be validated.

### 3. Solution Design

Design the smallest sound solution that fits the current system:

- System architecture and component boundaries
- Data model or schema changes
- API or contract changes
- Integration points and failure modes
- Backward compatibility strategy
- Migration or rollout sequencing
- Logging, metrics, tracing, dashboards, and alerts
- Operational ownership and runbook needs

If multiple designs are plausible, compare them briefly and recommend one based on correctness, safety, maintainability, reversibility, and delivery speed.

### 4. Implementation Plan

Translate the design into an executable plan:

- Break work into milestones or phases
- Define entry and exit criteria for each phase
- Sequence code, config, infra, schema, and documentation changes
- Identify feature flags, canarying, or guarded rollouts when needed
- Separate must-have work from optional follow-ups

Prefer plans that can stop safely after each phase.

### 5. Debugging And Root-Cause Plan

For risky or failure-prone work, include:

- Expected failure modes
- Reproduction strategy
- Signals to inspect: logs, traces, metrics, events, state transitions
- Isolation steps to narrow the fault domain
- Root-cause criteria
- Regression protections to add after the fix

Do not propose speculative fixes without an evidence path.

### 6. Validation Strategy

Map work to the right test layers:

- Unit tests for isolated logic
- Integration tests for boundaries and dependencies
- End-to-end or smoke tests for critical flows
- Migration or schema validation
- Security checks for exposed surfaces
- Performance checks for critical paths
- Release-readiness checks such as lint, typecheck, build, packaging, and config validation

For each validation step, state:

- Purpose
- Preconditions
- Command or mechanism when known
- Pass/fail signal

### 7. Integration And Release Plan

Before release, cover:

- Backward compatibility checks
- Dependency or config changes
- Secret or credential handling
- Build artifact expectations
- Release notes or change communication
- Support and ownership expectations

Block release when a critical gate cannot be satisfied safely.

### 8. Deployment And Rollback Plan

Describe:

- Target environments
- Pre-deploy checks
- Rollout strategy such as canary, blue/green, feature flag, or staged rollout
- Immediate post-deploy smoke checks
- Metrics and alerts to watch
- Explicit rollback triggers
- Rollback actions and recovery expectations

If production deployment is out of scope, mark it as pending rather than inventing a rollout.

### 9. Production Verification

Define how to confirm success in the live environment:

- Acceptance criteria checks
- Health indicators and SLIs
- Error-rate or latency guardrails
- Dashboard and log review points
- Verification window and ownership

### 10. Outcome Documentation

Close with:

- Delivery summary
- Validation evidence or planned evidence
- Residual risks
- Deferred follow-ups
- Operational notes for the next engineer

## Output Format

Use one of these modes:

- Concise mode: deliver the plan directly in the reply with clear section headers.
- Artifact mode: create or update delivery docs in `delivery/` for complex or long-running work.

When artifact mode is appropriate, read [references/delivery-artifacts.md](references/delivery-artifacts.md) and use only the subset of files needed for the task.

## Quality Bar

Reject weak plans. Improve them until they are:

- Specific to the codebase and environment
- Testable
- Sequenced
- Operationally safe
- Honest about unknowns
- Actionable by another engineer without extra interpretation
