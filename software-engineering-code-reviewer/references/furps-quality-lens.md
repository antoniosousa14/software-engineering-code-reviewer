# FURPS+ Quality Lens

Use FURPS+ as a practical review lens for code and architecture. Do not turn it into a scorecard. Use it to reveal missing requirements, weak trade-offs, and quality risks.

## Functionality

Check whether the code does the right thing.

- Does it satisfy the stated behavior?
- Are important business rules represented clearly?
- Are edge cases and failure paths handled?
- Are invalid states prevented or detected?
- Are integrations and side effects correct?

## Usability

For user-facing code, review the experience. For developer-facing code, review the API and maintenance experience.

- Is the public interface easy to use correctly?
- Are error messages actionable?
- Are defaults safe and unsurprising?
- Can another engineer understand how to call, extend, or debug it?

## Reliability

Review how the code behaves under failure, repetition, and real operating conditions.

- Are errors handled at appropriate boundaries?
- Are retries, idempotency, timeouts, and partial failures considered when relevant?
- Are resources cleaned up?
- Are concurrency or ordering hazards present?
- Are invariants protected consistently?

## Performance

Review performance relative to realistic constraints.

- Are algorithms and data structures reasonable for expected scale?
- Are expensive operations repeated unnecessarily?
- Are database, network, filesystem, or rendering operations batched or bounded when needed?
- Is optimization justified by constraints or evidence?

## Supportability

Review how easy the code is to change, test, operate, and debug.

- Is the code modular and cohesive?
- Are volatile details isolated?
- Can meaningful behavior be tested without heavy infrastructure?
- Is logging, telemetry, or diagnostics sufficient for production issues when applicable?
- Are names and boundaries clear enough for future maintenance?

## Plus constraints

Review additional constraints that shape acceptable design.

- Security and privacy
- Compliance and auditability
- Deployment and runtime environment
- Compatibility with existing architecture
- Team conventions and language idioms
- Licensing, dependency, and operational constraints

Use constraints to avoid generic advice. A good recommendation fits the codebase, runtime, team, and risk level.
