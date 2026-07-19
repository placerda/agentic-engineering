# Minimal specification flow

This directory offers a lightweight flow inspired by specification-driven
development. It does not embed or depend on a third-party distribution.

Use the objective rule in `memory/constitution.md`.

## Sequence

1. Copy `templates/spec-template.md` to
   `.specify/specs/NNN-short-name/spec.md`.
2. Resolve questions that alter behavior, data, security, or contract.
3. Copy `templates/plan-template.md` to `plan.md` in the same directory.
4. Record significant architectural decisions in `docs/adr/`.
5. Break the delivery into small tasks, each with a verification condition.
6. Update the specification and plan when a decision changes. Do not let
   the code be the only source of the new behavior.

Keep the specification focused on the what and the why. The plan describes
the how, order, migration, and validation.

