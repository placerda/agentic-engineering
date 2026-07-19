# Implementation practices and clean code

Use these practices to keep implementation readable, testable, and easy to
change.

## Clarity

- Use names that express intent, unit, and domain. Avoid local
  abbreviations without value.
- Keep functions focused on one outcome and at the same level of
  abstraction.
- Prefer explicit flow over hidden side effects.
- Reduce nesting with clear validations, decomposition, and suitable
  models.
- Comments explain reason, risk, or constraint. They do not narrate
  confusing code.

## Design

- Remove duplication of knowledge, not just similar-looking text.
- Encapsulate invariants near the data and behavior that maintain them.
- Do not add parameters, flags, or abstractions for hypothetical
  scenarios.
- Make invalid states hard to represent when the cost is reasonable.
- Keep contracts small and cohesive. Avoid objects that know details from
  many layers.

## Errors

- Fail with useful context and at the level that can make a decision.
- Do not catch broad exceptions to return apparent success.
- Preserve the original cause when translating errors across boundaries.
- Messages must not expose a secret, personal data, or exploitable detail.
- Model recovery and idempotency for repeatable effects.

## Safe change

- Read tests and call sites before changing an interface.
- Make the smallest complete change and keep refactoring separate when
  possible.
- Delete dead code instead of commenting out old versions.
- Use the formatter, linter, static analysis, and tests configured by the
  project.
