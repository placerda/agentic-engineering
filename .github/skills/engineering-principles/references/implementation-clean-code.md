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

- Remove duplicated knowledge, not just similar-looking text.
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

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- Martin, Robert C.
  [*Clean Code: A Handbook of Agile Software Craftsmanship*](https://www.oreilly.com/library/view/clean-code-a/9780136083238/).
  Prentice Hall, 2008.
- Hunt, Andrew; Thomas, David.
  [*The Pragmatic Programmer*](https://pragprog.com/titles/tpp20/the-pragmatic-programmer-20th-anniversary-edition/).
  20th Anniversary ed. Addison-Wesley, 2019.
- Fowler, Martin.
  [*Refactoring: Improving the Design of Existing Code*](https://martinfowler.com/books/refactoring.html).
  2nd ed. Addison-Wesley, 2018.
