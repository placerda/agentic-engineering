---
name: python-development
description: Guides Python implementation and review aligned with PEP 8, PEP 20, PEP 257, and the repository's tools. Use when changing Python files.
---

# Python development

Read `../engineering-principles/references/python-pep-guidance.md`. Then:

1. Discover the Python version, package manager, `pyproject.toml`, and real
   commands.
2. Preserve types, the public API, and behavior.
3. Apply docstrings where the public contract needs them.
4. Isolate external effects and cover rules with deterministic tests.
5. Run the linter, formatter, type checker, and tests already configured.

Do not impose a line limit or tool different from the project's
configuration. Do not use `Any`, casts, or broad exception handling to work
around a design error.

