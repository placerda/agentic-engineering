# Characteristics, trade-offs, and decisions

## Prioritize

- Derive characteristics from the domain, constraints, and risks, not from
  a generic list.
- Choose a small set of important characteristics, such as availability,
  security, modifiability, performance, or auditability.
- Make each characteristic observable with a scenario, stimulus,
  environment, response, and measure.
- Distinguish a global characteristic from one restricted to a single flow
  or component.

## Analyze

- Every improvement has a cost or side effect. State what was sacrificed.
- Compare alternatives in context. Include cognitive complexity, operation,
  data, delivery, cost, and reversibility.
- Start with the smallest degree of distribution that meets the measures.
- Metrics are signals for investigation, not standalone targets. When a
  measure becomes a goal, it can lose diagnostic value.

## Record the decision

Use an ADR when the decision:

- alters a relevant boundary, contract, data, or characteristic;
- is expensive to reverse;
- restricts future alternatives;
- affects more than one component or team;
- needs automated oversight.

Record context, forces, alternatives, decision, consequences, adoption
plan, and compliance checks. Do not rewrite an accepted ADR to erase
history. Replace it with another ADR.

## Fitness functions

Turn objective rules into checks: dependency tests, latency limits, schema
compatibility, policies, static analysis, resilience tests, or alerts. A
rule without an inspection method tends to degrade.

