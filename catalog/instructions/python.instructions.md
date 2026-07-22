---
applyTo: "**/*.py,**/*.pyi"
---

# Python

- The repository's executable configuration is the source of truth. Respect
  `pyproject.toml`, Ruff, the formatter, the type checker, and the tests
  already adopted. Do not replace local choices with generic preferences.
- Follow PEP 8 for readability, naming, imports, spacing, and organization,
  unless the project's configuration defines a different compatible
  convention.
- Apply PEP 20 as a decision criterion: be explicit, simple, and readable;
  do not hide errors; when facing meaningful ambiguity, refuse to guess.
- Follow PEP 257 for public modules, classes, functions, and methods.
  Docstrings must explain behavior, contract, arguments, return value, side
  effects, exceptions, and constraints when that information is useful. Do
  not repeat the signature or describe the obvious.
- Prefer precise types, small structures, and explicit interfaces. Avoid
  `Any`, casts, and broad exceptions without justification.
- Isolate clock, randomness, filesystem, network, and providers so business
  logic is deterministically testable.
- Run Ruff, the formatter, type checking, and tests according to the
  repository's commands. Do not introduce new tools just to satisfy this
  rule.

For deeper guidance, read
`.github/skills/engineering-principles/references/python-pep-guidance.md`.
