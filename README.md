# Agentic Engineering

A reusable model for guiding software engineering agents on GitHub and
GitHub Copilot without turning every request into a lengthy manual.

The repository uses progressive disclosure:

1. A short core applies to all work.
2. Specific instructions load only for matching files.
3. Functional agents take on roles with minimal tools.
4. Skills load procedures and references only when relevant.
5. Documentation in `docs/` provides human guidance and loads only when
   referenced.

## Quick start

1. Start with the [`adoption guide`](docs/adoption-guide.md) and adapt the
   template to the repository's real tools and process.
2. Choose the agent from [`docs/routing.md`](docs/routing.md).
3. For a simple change, work from an issue with acceptance criteria. For a
   broad or high-risk change, resolve contract, data, security,
   migration, and recovery decisions before implementation.
4. Run the repository's relevant checks and record reproducible evidence.

[`AGENTS.md`](AGENTS.md) is the operating contract Copilot reads. Maintainers
should review and adapt it before using the template.

## Repository map

| Path | Purpose |
| --- | --- |
| `.github/copilot-instructions.md` | Concise, always-on core |
| `.github/instructions/` | Path-activated rules |
| `.github/agents/` | Functional agents and their boundaries |
| `.github/skills/` | Indexes and procedures loaded on demand |
| `docs/` | Full guide, adoption, and routing |
| `docs/adr/` | Architectural decisions of the consuming project |

## Adopting this in another repository

Do not copy everything without analysis. Start with the core, replace commands
and paths with ones that have been successfully run in the project, remove
unused agents, and enable only the instructions compatible with the present
technology. The full roadmap is in
[`docs/adoption-guide.md`](docs/adoption-guide.md).

## Add GitHub Spec Kit

[GitHub Spec Kit](https://github.com/github/spec-kit) is a separate official
open-source GitHub project for specification-driven development.

In each consuming project, follow the official
[installation guide](https://github.com/github/spec-kit/blob/main/docs/installation.md)
to install `specify-cli`, then run this from the repository root:

```shell
specify init --here --force --integration copilot --integration-options="--skills"
```

This template has no pre-populated `.specify/` files. Initializing each
consuming project ensures generated files match its Spec Kit version, Copilot
integration mode, and execution environment. In Spec Kit 0.13.2, skills mode
is the modern Copilot layout; the legacy `.agent.md` plus `.prompt.md` layout
is deprecated. Generated skills are supported by GitHub Copilot App.

See the [adoption guide](docs/adoption-guide.md#7-add-spec-kit-when-needed) for
environment-specific commands and generated files to review and version.

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
