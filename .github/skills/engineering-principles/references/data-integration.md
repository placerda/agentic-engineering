# Data and integration

## Data

- Data ownership follows the capability responsible for its semantics.
- Integration through a shared database reduces autonomy and creates
  hidden contracts.
- Choose data topology together with boundaries and operation, not
  afterward.
- Schema changes need compatibility, migration, observation, and
  recovery.
- Minimize copies, but accept controlled duplication when it reduces
  coupling and has a clear consistency rule.

## Communication

- Synchronous calls are simple to reason about locally, but couple
  availability, latency, and capacity.
- Asynchronous messages decouple time and can improve resilience, but
  require idempotency, ordering when needed, duplicate handling,
  tracing, and operation.
- Define timeout, retry, backoff, circuit breaker, and latency budget at
  the appropriate level. Unbounded retries amplify failures.
- Contracts must have error semantics and compatible evolution.

## Orchestration and choreography

- Use orchestration when a flow needs explicit coordination, visible
  state, central compensation, or step auditing.
- Use choreography when participants can react independently and coupling
  to a coordinator would be more expensive.
- Avoid opaque choreography with an implicit, hard-to-observe event
  sequence.
- For critical flows, model partial failures and compensations before
  implementation.

## Evidence

Test contracts, compatibility, idempotency, partial failures, recovery, and
correlation telemetry. A happy-path diagram does not prove safe operation.

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- Newman, Sam.
  [*Building Microservices*](https://www.oreilly.com/library/view/building-microservices-2nd/9781492034018/).
  2nd ed. O'Reilly Media, 2021.
- Nygard, Michael T.
  [*Release It!*](https://pragprog.com/titles/mnee2/release-it-second-edition/).
  2nd ed. Pragmatic Bookshelf, 2018.
- Hohpe, Gregor; Woolf, Bobby.
  [*Enterprise Integration Patterns*](https://www.enterpriseintegrationpatterns.com/).
  Addison-Wesley, 2003.
- Richardson, Chris.
  [*Microservices Patterns*](https://www.manning.com/books/microservices-patterns).
  Manning, 2018.
