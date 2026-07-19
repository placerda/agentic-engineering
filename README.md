# Agentic Engineering

A reusable model for guiding software engineering agents on GitHub and
GitHub Copilot without turning every request into a lengthy manual.

The repository uses progressive disclosure:

1. A short core applies to all work.
2. Specific instructions load only for matching files.
3. Functional agents take on roles with minimal tools.
4. Skills load procedures and references only when relevant.
5. Documentation in `docs/` serves people and can be opened when a skill or
   instruction points to it. It is not automatic context.

Spec Kit, in `.specify/`, is triggered by an objective rule for high-risk
changes. It is a workflow, not a context layer.

## Quick start

1. Read [`AGENTS.md`](AGENTS.md) to learn the operating contract.
2. Choose the agent from the table in [`docs/routing.md`](docs/routing.md).
3. For a simple change, work from an issue with acceptance criteria.
4. For a broad or high-risk change, follow
   [`.specify/README.md`](.specify/README.md).
5. Before concluding, produce reproducible evidence that the expected
   behavior works.

## Repository map

| Path | Purpose |
| --- | --- |
| `.github/copilot-instructions.md` | Concise, always-on core |
| `.github/instructions/` | Path-activated rules |
| `.github/agents/` | Functional agents and their boundaries |
| `.github/skills/` | Indexes and procedures loaded on demand |
| `.specify/` | Constitution and minimal specification flow |
| `docs/` | Full guide, adoption, and routing |
| `docs/adr/` | Architectural decisions of the consuming project |

## Adopting this in another repository

Do not copy everything without analysis. Start with the core, replace commands
and paths with ones that have been successfully run in the project, remove
unused agents, and enable only the instructions compatible with the present
technology. The full roadmap is in
[`docs/adoption-guide.md`](docs/adoption-guide.md).

## Automatic discovery and common references

GitHub Copilot recognizes files in specific locations and formats. Files such
as `.github/copilot-instructions.md`, `AGENTS.md`, profiles in
`.github/agents/`, `*.instructions.md` instructions, and skills with
`SKILL.md` can be discovered by compatible surfaces. A plain Markdown file in
`docs/` is not automatically loaded just by existing. It needs to be
attached, referenced by a compatible instruction, or opened when a skill
directs its use.

Support varies across GitHub.com, Copilot CLI, and IDEs. Check
[`docs/agentic-development-model.md`](docs/agentic-development-model.md#cross-surface-compatibility)
before relying on a specific feature.

## Sources and licensing

The model draws on established software architecture, implementation, Python,
cloud-native, and agentic engineering guidance. The complete bibliography is in
[`sources.md`](.github/skills/engineering-principles/references/sources.md).

This repository does not declare a license. Define an appropriate license
before redistributing the model.
