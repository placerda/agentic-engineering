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

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- Martin, Robert C. [*Clean Architecture: A Craftsman's Guide to Software
  Structure and Design*](https://www.oreilly.com/library/view/clean-architecture-a/9780134494272/).
  Pearson Education, 2017. See the component cohesion and dependency principles.
- Richards, Mark; Ford, Neal.
  [*Fundamentals of Software Architecture*](https://fundamentalsofsoftwarearchitecture.com/).
  O'Reilly Media. See the material on modularity, component-based thinking,
  coupling, and connascence.
- Skelton, Matthew; Pais, Manuel.
  [*Team Topologies*](https://teamtopologies.com/book).
  IT Revolution, 2019.
- Conway, Melvin.
  ["How Do Committees Invent?"](https://www.melconway.com/Home/Committees_Paper.html).
  *Datamation*, 1968.
