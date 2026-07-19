# Components and boundaries

## Where to draw boundaries

- Draw boundaries by axes of change, ownership, volatility, risk, and
  architectural characteristics, not by trend or a momentary org chart.
- Group what changes for the same reason. Separate what changes for
  different reasons.
- Consider who publishes, deploys, and supports the component.
- Start with logical independence. Distribute physically only when scale,
  isolation, deployment, compliance, or ownership justify the cost.

## Cohesion and coupling

- Evaluate whether the component's elements contribute to a common
  purpose.
- Measure static, temporal, data, and operational dependencies.
- Keep the dependency graph between components acyclic.
- Synchronous dependencies create operational coupling in availability,
  latency, and capacity. Include that cost in the decision.
- Stable elements should depend on useful abstractions; abstractions
  without users or variation just hide complexity.

## Boundary contracts

- Data crossing boundaries belongs to explicit, minimal, versionable
  contracts.
- Do not transport entire internal objects for convenience.
- Define error semantics, idempotency, timeout, compatibility, and
  ownership.
- A partial boundary can be enough when it offers code and test isolation
  without the cost of a process or network hop.

## Heuristics

- Prefer a modular monolith to premature services.
- Reuse deliberately. Sharing code also shares change calendar and
  regression risk.
- Align boundaries, data, and team ownership whenever possible.
- Reassess granularity when components change together, require frequent
  coordination, or cannot be operated independently.

