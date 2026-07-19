# Architecture core

## Purpose

- The organization of the system should reveal business capabilities and
  language, not just frameworks or technical types.
- Architecture exists to keep important options open and to reduce the
  total cost of changing, operating, and verifying the system.
- There is no universally best style. Every choice responds to context,
  constraints, and trade-offs.

## Direction of dependencies

- Code dependencies point toward stable policies and domain rules.
- Interface, persistence, transport, framework, and provider are
  replaceable mechanisms, not the center of the model.
- ORM, HTTP, messaging, or SDK models must not cross the core. Convert them
  to minimal contracts at the boundary.
- The flow of execution can leave the core, but the code dependency keeps
  pointing inward through ports, callbacks, or interfaces.

## Decisions

- Separate policy from mechanism. Policy describes what should happen;
  mechanism describes how an environment carries it out.
- Prefer reversible decisions while knowledge is still low.
- Defer details without blocking essential learning.
- Justify abstractions by stability, concrete variation, or protecting a
  boundary. Avoid speculative generality.
- Treat architecture as a continuous activity. Check whether
  implementation, data, delivery, observability, and operation still
  express the decision.

## Review questions

1. What business capability does this structure make evident?
2. Can the core run without a UI, network, database, clock, or real
   provider?
3. Which detail would have the highest replacement cost today?
4. Is the dependency oriented toward the most stable part?
5. What evidence shows the decision works under the real constraints?

