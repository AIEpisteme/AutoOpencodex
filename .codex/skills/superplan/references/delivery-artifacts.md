# Delivery Artifacts

Use these templates when the task is large enough to justify persistent delivery docs. Do not create all files by default. Create only the files that materially improve execution or handoff.

## `delivery/README.md`

Use as the index for complex efforts.

Suggested sections:

- Objective
- Scope
- Current status
- Linked artifacts
- Owners or stakeholders
- Open risks

## `delivery/plan.md`

Suggested sections:

- Problem statement
- Goals
- Non-goals
- Constraints
- Assumptions
- Risks and unknowns
- Milestones
- Validation strategy
- Rollback strategy

## `delivery/requirements.md`

Suggested sections:

- Functional requirements
- Non-functional requirements
- Interfaces and contracts
- Data requirements
- Error handling expectations
- Security requirements
- Acceptance criteria
- Requirement-to-validation mapping

## `delivery/design.md`

Suggested sections:

- Architecture summary
- Component boundaries
- Data model or schema changes
- API or integration changes
- Failure modes
- Backward compatibility
- Observability plan
- Rollout considerations

## `delivery/test-plan.md`

Suggested sections:

- Test objectives
- Unit coverage
- Integration coverage
- End-to-end or smoke coverage
- Migration validation
- Security checks
- Performance checks
- Release gates
- Evidence to capture

## `delivery/release-checklist.md`

Suggested sections:

- Environment readiness
- Config and secrets
- Build and artifact checks
- Migration checks
- Rollout steps
- Smoke tests
- Monitoring checks
- Rollback trigger and action

## `delivery/production-runbook.md`

Suggested sections:

- Service overview
- Deployment procedure
- Health indicators
- Alert response
- Common failure modes
- Rollback procedure
- Escalation notes

## Usage Notes

- Keep docs concise and operational.
- Prefer checklists and decision-ready notes over long essays.
- Mark anything unverified as pending.
- Update the docs as execution changes the plan.
