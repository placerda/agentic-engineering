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
- Metrics are signals for investigation, not standalone targets. Review them
  with the behavior and trade-offs they represent.

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

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- Richards, Mark; Ford, Neal.
  [*Fundamentals of Software Architecture*](https://fundamentalsofsoftwarearchitecture.com/).
  O'Reilly Media.
- Bass, Len; Clements, Paul; Kazman, Rick.
  [*Software Architecture in Practice*](https://www.oreilly.com/library/view/software-architecture-in/9780136885979/).
  4th ed. Addison-Wesley, 2021.
- Nygard, Michael.
  ["Documenting Architecture Decisions"](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html).
  2011.
- Ford, Neal; Parsons, Rebecca; Kua, Patrick; Sadalage, Pramod.
  [*Building Evolutionary Architectures*](https://evolutionaryarchitecture.com/).
  2nd ed. O'Reilly Media, 2022.
