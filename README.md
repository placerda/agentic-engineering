# Agent-Native Engineering

A practical GitHub Copilot starter template for repositories where agents do
real engineering work, not just autocomplete.

The template is ready to use with a deliberately small active core. It includes
two custom agents, foundational skills, and issue and pull request templates.
Additional agents, skills, and stack-specific instructions live in `catalog/`
and are not discovered automatically. Activate only what the project needs.

## Start here

1. Create a repository from this template, or copy the template files into an
   existing repository.
2. Open the repository in GitHub Copilot App, CLI, or a supported IDE. Choose
   the prompt that matches the project.

   **Existing repository**

   ```text
   Inspect the manifests, scripts, CI workflows, source tree, tests, and
   documentation in this repository. Compare that evidence with AGENTS.md and
   the files under .github/. Propose only changes supported by what you find,
   list the commands you verified, and flag anything that still needs a human
   decision. Do not edit yet.
   ```

   **New project**

   ```text
   This is a new project for [describe the product in one sentence]. Before
   editing, ask me only for decisions that cannot be discovered yet, such as
   the stack, commands, source layout, deployment target, and quality gates.
   Then propose the smallest agent-native setup that fits those decisions. Do
   not edit yet.
   ```

3. Review the proposal, let Copilot apply the approved changes, then start with
   a small issue that has a clear
   outcome and acceptance criteria.

That is enough to begin. The
[`Agent-Native Engineering guide`](docs/agent-native-engineering.md) explains
the model and every customization point.

## What you get

| Area | Included |
| --- | --- |
| Core behavior | `AGENTS.md` and `.github/copilot-instructions.md` |
| Active agents | `implementation` and `architecture` |
| Active skills | Engineering principles and architecture decisions |
| Optional catalog | Triage, support, documentation, orchestration, communications, Python, and cloud-native components |
| Workflow | Issue and pull request templates with evidence and risk prompts |
| Human guide | One concise guide in `docs/` |

Start with the `implementation` agent for normal development work. Use
`architecture` only for structural or hard-to-reverse decisions.

## Customize only what you need

- Replace generic project facts and commands with verified ones.
- Copy stack-specific instructions or skills from `catalog/` only when they
  match the project.
- Add another agent only for a recurring, well-defined role.
- Adapt issue and pull request templates to the team's real process.
- Review external skills before placing them in `.github/skills/`.

The guide maps each file to its purpose and explains when to change it.

## Avoid overlapping agents and skills

Keep one active component for each capability. Before adding an agent or skill
from another repository or plugin, compare its job with what is already active:

- replace an equivalent component;
- merge the useful rules into the existing component; or
- skip it.

Do not keep two implementation agents, two architecture agents, or competing
planning skills active by default. Spec Kit's `speckit-*` skills can coexist
with this core because they provide a named specification workflow rather than
another general implementation agent.

## Optional: add GitHub Spec Kit

[GitHub Spec Kit](https://github.com/github/spec-kit) adds a
specification-driven workflow. It is optional and generated per project.

1. Install `specify-cli` using the official
   [installation guide](https://github.com/github/spec-kit/blob/main/docs/installation.md).
2. From the repository root, run the command for the environment:

   **Windows with PowerShell**

   ```powershell
   specify init --here --force --integration copilot `
     --integration-options="--skills" --script ps
   ```

   **Linux or cloud**

   ```shell
   specify init --here --force --integration copilot \
     --integration-options="--skills" --script sh
   ```

3. Review and commit the generated `.github/skills/speckit-*` and `.specify/`
   files.

The template does not pre-populate those files because Spec Kit generates
environment-specific scripts. These commands were verified with Spec Kit
0.13.2 and the generated skills were discovered by GitHub Copilot App.

## How Copilot loads this setup

- Core instructions are discovered from their standard repository locations.
- Scoped instructions apply only to matching files.
- Agents and skills are loaded when selected or relevant.
- Files under `catalog/` remain inactive until copied to a supported
  `.github/` location.
- The guide in `docs/` is human reference material and is read only when opened
  or referenced.

Feature availability can vary across GitHub.com, Copilot App, CLI, and IDEs.

## Sources and licensing

The model draws on established software architecture, implementation, Python,
cloud-native, and agentic engineering guidance. The bibliography is in
[`sources.md`](.github/skills/engineering-principles/references/sources.md).

This repository does not declare a license. Define an appropriate license
before redistributing the model.
