# Testing and fitness functions

## Architectural testability

- Business rules must run without a real UI, network, database, clock, or
  provider.
- Inject external effects through small contracts. Use real
  implementations in focused integration tests.
- Control time, randomness, and concurrency to maintain determinism.
- If an important behavior can only be tested through a full journey, the
  architecture is probably hiding useful boundaries.

## Strategy

- Unit tests protect local rules and decisions.
- Contract tests protect boundaries between consumers and providers.
- Integration tests protect adapters and real configuration.
- A few end-to-end tests protect critical journeys.
- Tests must observe behavior, not the internal way it is implemented.
- A defect should gain an automated reproduction when the cost is
  reasonable.

## Fitness functions

Automate rules that must remain true, for example:

- the domain does not import infrastructure;
- the component graph contains no cycles;
- APIs and events preserve compatibility;
- latency, availability, or cost stay within budget;
- images and dependencies meet security policies;
- migrations support cross-version coexistence;
- telemetry contains the signals needed to operate.

Choose the cheapest execution point that still detects the violation in
time: IDE, pre-commit, test, CI, deployment, or monitoring.

## Completion evidence

Record command, scope, result, and limitations. Coverage is a signal, not
proof of quality. A task is incomplete if the expected result cannot be
verified.

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- Ford, Neal; Parsons, Rebecca; Kua, Patrick; Sadalage, Pramod.
  [*Building Evolutionary Architectures*](https://evolutionaryarchitecture.com/).
  2nd ed. O'Reilly Media, 2022.
- Fowler, Martin.
  ["The Practical Test Pyramid"](https://martinfowler.com/articles/practical-test-pyramid.html).
  2018.
- Fowler, Martin.
  ["Contract Test"](https://martinfowler.com/bliki/ContractTest.html).
- Humble, Jez; Farley, David.
  [*Continuous Delivery*](https://www.oreilly.com/library/view/continuous-delivery-reliable/9780321670250/).
  Addison-Wesley, 2010.
