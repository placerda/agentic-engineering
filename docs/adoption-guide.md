# Adoption guide

This model is a starting point. Adopt only rules that can be explained,
maintained, and verified in the target repository.

## 1. Take inventory

Record:

- purpose, users, and product capabilities;
- languages, frameworks, and runtimes;
- real bootstrap, build, test, lint, and run commands;
- module structure and ownership;
- public interfaces, persisted data, and deployment units;
- CI, security policies, and release process;
- canonical documentation and operational channels.

Run the commands before documenting them. Do not copy examples from this
model as if they were the project's commands.

## 2. Adopt the core

Copy `AGENTS.md` and `.github/copilot-instructions.md`. Then:

1. Replace generic language with stable facts from the repository.
2. Keep the always-on file short.
3. Remove any rule that contradicts existing automation.
4. Add the validated commands and the most important paths.
5. Do not include secrets, private URLs with tokens, or personal data.

## 3. Enable real scope

Copy `python.instructions.md` only if there is Python. Confirm the
`**/*.py,**/*.pyi` glob covers the project.

Copy `cloud-native.instructions.md` only if the repository contains
deployable services or infrastructure. Adjust `applyTo` to the real
directories. Do not use a broad `**/*.yaml`, as that would apply
cloud-native rules to files unrelated to deployment.

Create new scoped instructions only when:

- the rule applies to an identifiable set of files;
- the glob is specific;
- the rule will be used frequently;
- there is no equivalent executable configuration.

## 4. Choose agents

Start with `implementation` and, if needed, `architecture`. Add other
profiles when there is recurring demand and a distinct output.

For each profile:

- keep a functional name;
- write when to use it and when not to in the description;
- grant the smallest set of tool aliases needed;
- do not configure MCPs or secrets without a security review;
- define input, output, and handoff.

Many agents increase routing, duplication, and maintenance. Few broad
agents increase context and mixed responsibilities. Add an agent when the
specialization has its own criteria, tools, or artifacts.

## 5. Choose skills

Copy `engineering-principles` as the canonical library. Remove references
that do not apply. Focused skills should point to the canonical rule, not
duplicate it.

Review any external skill before installing it. Skills can contain
malicious scripts and instructions. Do not pre-approve shell in
`allowed-tools` without trust and need.

## 6. Configure issue templates and planning

Adapt the issue templates and planning expectations to the real process:

- a direct issue for a local, reversible change;
- explicit decisions about contracts, data, security, migration, and recovery
  for broad or high-risk work.

Avoid requiring extensive planning for simple fixes. Also avoid using a vague
issue for data migration, security change, or an incompatible contract.

## 7. Add Spec Kit when needed

Adopt [GitHub Spec Kit](https://github.com/github/spec-kit) when the project
needs a specification-driven workflow. Install `specify-cli` 0.13.2 and
initialize it from the consuming project's repository root.

For local Windows, select PowerShell scripts and skills mode:

```shell
specify init --here --force --integration copilot --integration-options="--skills" --script ps
```

For Linux or a cloud environment, select shell scripts and skills mode:

```shell
specify init --here --force --integration copilot --integration-options="--skills" --script sh
```

Skills mode is the modern layout in Spec Kit 0.13.2. The legacy `.agent.md`
plus `.prompt.md` layout is deprecated. Review and version the generated
`.github/skills/speckit-*` files and required `.specify/` infrastructure so
GitHub Copilot App worktrees can use them. Initialize the consuming project
instead of copying `.specify/` from this template. This keeps generated files
aligned with the project's Spec Kit version, Copilot integration mode, and
execution environment.

The expected result is a generated skills integration and its supporting
Spec Kit infrastructure. If `specify` is unavailable or an option is rejected,
verify the CLI installation and version, then rerun the command. Review
conflicts and partial generated changes before retrying with `--force`.

## 8. Integrate quality

This repository does not provide an executable workflow because it does
not know the target stack. In the consuming project, connect fitness
functions to the mechanisms already adopted:

- formatter, linter, and type checker;
- unit, contract, integration, and journey tests;
- dependency and cycle analysis;
- code, dependency, and secret security;
- schema and infrastructure validation;
- metrics and deployment policies.

Each gate needs an owner, acceptable time, actionable message, and an
exception process.

## 9. Run a pilot

Choose a real, low-risk change and observe:

- instructions discovered correctly;
- irrelevant files loaded;
- repeated questions;
- missing tool or permission;
- handoff quality;
- time to first valid change;
- rework after review;
- evidence produced.

Adjust the model based on these signals, not on the volume of files.

## Checklist

- [ ] The core contains stable facts and verified commands.
- [ ] Scoped instructions have specific globs.
- [ ] Each agent has a use case, non-use case, tools, and output.
- [ ] Skills have one canonical source per rule.
- [ ] Planning depth reflects the product's risk.
- [ ] Templates reflect the team's process.
- [ ] Spec Kit generated files are reviewed and versioned when it is adopted.
- [ ] CI runs important objective rules.
- [ ] Links, names, and paths have been verified.
- [ ] An owner and periodic review have been defined.
