# Engineering constitution

## I. Purpose and behavior

Software must express domain capabilities and deliver observable behavior.
Frameworks, databases, interfaces, and providers are mechanisms. Changes
start from the problem, user, outcome, and acceptance criteria.

## II. Dependencies and boundaries

Dependencies point toward stable policies. Data crosses boundaries through
explicit, minimal contracts. Boundaries follow change, ownership,
volatility, and risk. Component graphs remain acyclic.

## III. Simplicity and reversibility

Use the smallest degree of distribution and abstraction that satisfies
measured requirements. Prefer logical independence before physical
distribution and reversible decisions while knowledge is still low.

## IV. Verifiable quality

Objective rules become tests, static analysis, policies, or observation.
Business rules must be testable without real infrastructure. Tests protect
behavior and contracts.

## V. Security and operation

Least privilege, secrets kept out of code, untrusted input, and failure
recovery are design requirements. Code, data, delivery, observability, and
operation must remain aligned.

## VI. Evidence

Work does not end with code produced. Acceptance criteria, validations,
affected documentation, migration, and residual risks need reproducible
evidence.

## When Spec Kit is mandatory

Use the flow in `.specify/` if any high-risk condition occurs:

- a change to authentication, authorization, encryption, privacy, or a
  trust boundary;
- a data migration with potential for loss, corruption, or unavailability;
- an incompatible public contract without a coexistence strategy.

Also use Spec Kit when **two or more** of the following are true:

- the change crosses three or more components or deployment units;
- it requires a new boundary, architectural style, or operational
  technology;
- it affects an API, event, persisted schema, or external integration;
- it has a measurable architectural characteristic as a primary
  requirement;
- it involves more than one team or delivery across multiple stages;
- it remains uncertain after a short investigation;
- it has an expensive reversal or requires coordinated migration.

Use direct work through an issue when the change is local, reversible, fits
within one component, does not alter a persisted or public contract, and
has verifiable acceptance criteria. Do not create a specification just for
the sake of formality.

## Amendments

Changes to this constitution require justification, an impact assessment
on existing artifacts, and an adoption plan. Rules that cannot be verified
must be rewritten or explicitly treated as heuristics.

**Version:** 1.0.0<br>
**Ratified on:** 2026-07-19
