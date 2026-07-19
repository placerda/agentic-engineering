# Python based on PEP 8, PEP 20, and PEP 257

## Source of truth

`pyproject.toml` and the configurations for Ruff, the formatter, the type
checker, and the tests are executable and take precedence over generic
preferences. Do not introduce a tool if the project already has an
equivalent one.

## PEP 8

- Optimize for consistent readability.
- Use names that express intent and follow the codebase's conventions.
- Organize imports and avoid wildcard imports.
- Separate logical blocks without creating visual fragmentation.
- Respect the configured line length. When there is no configuration, use
  the official recommendation as a starting point.
- Local consistency matters, but do not perpetuate a violation that the
  project's automation rejects.

## PEP 20

- Prefer explicit over implicit and simple over complicated.
- Readability is a requirement, not a finishing touch.
- Do not let errors pass silently without an explicit decision.
- When facing ambiguity with impact, do not guess.
- If an implementation is hard to explain, reduce it or record the reason.

## PEP 257

- Document public modules and APIs.
- Docstrings summarize behavior and contract, not the signature.
- Include arguments, return value, side effects, exceptions, and
  constraints when relevant to correct use.
- Use a one-liner for simple cases; use a summary, blank line, and details
  for larger contracts.
- Document the public behavior of classes and any extension or override
  differences.

## Verification

Run, as configured in the project:

1. Ruff or an equivalent linter.
2. The formatter in check mode.
3. The static type checker.
4. Specific tests, then the required broader suite.

