# Agent-Native Engineering guide

Agent-native engineering means treating an agent as part of the engineering
system. The agent receives the right context, uses bounded tools, follows the
repository's real workflow, and proves the result.

This template already provides that starting point with a deliberately small
active core. You do not need to configure every file before using it.

## The model in one minute

The setup uses progressive disclosure:

1. `AGENTS.md` and `.github/copilot-instructions.md` define the small core that
   applies broadly.
2. `.github/instructions/` adds rules only for matching files.
3. `.github/agents/` provides the active implementation and architecture
   roles.
4. `.github/skills/` loads foundational procedures and references only when
   relevant.
5. `catalog/` holds optional components outside automatic discovery.
6. This guide explains the system to people without becoming automatic agent
   context.

The goal is not more instructions. It is the smallest useful context for the
work at hand.

## Use it before you customize it

Create a repository from the template and choose the path that matches the
project.

For an existing repository, let Copilot compare the template with evidence:

```text
Inspect the manifests, scripts, CI workflows, source tree, tests, and
documentation in this repository. Compare that evidence with AGENTS.md and the
files under .github/. Propose only changes supported by what you find, list the
commands you verified, and flag anything that still needs a human decision. Do
not edit yet.
```

For a new project, give Copilot the product goal and let it ask for missing
decisions:

```text
This is a new project for [describe the product in one sentence]. Before
editing, ask me only for decisions that cannot be discovered yet, such as the
stack, commands, source layout, deployment target, and quality gates. Then
propose the smallest agent-native setup that fits those decisions. Do not edit
yet.
```

Review the proposal and keep only verified facts or explicit decisions.
Copilot should discover real commands from an existing repository and verify
them before documenting them.

Then give the `implementation` agent a small issue with a clear outcome and
acceptance criteria. Use `architecture` only for a structural or
hard-to-reverse decision.

## What you can customize

| Path | What it does | Change it when |
| --- | --- | --- |
| `AGENTS.md` | Defines the stable operating contract Copilot reads | Engineering policy, risk rules, or evidence expectations differ |
| `.github/copilot-instructions.md` | Gives Copilot concise repository facts, commands, and important paths | Adopting the template in any real project |
| `.github/instructions/` | Contains active language or path-specific rules | A catalog instruction is activated or the directory layout changes |
| `.github/agents/` | Defines active specialist roles and their tool boundaries | A recurring role needs a distinct specialist |
| `.github/skills/` | Stores active reusable procedures and references | A trusted catalog or external skill is activated |
| `catalog/` | Stores optional components outside automatic discovery | A component is copied into its matching `.github/` directory |
| `.github/ISSUE_TEMPLATE/` | Captures outcomes, acceptance criteria, and risk | The team plans work differently |
| `.github/pull_request_template.md` | Captures validation and residual risk | The review process requires different evidence |

Delete what does not apply. A smaller accurate setup is better than a large
generic one.

## Activate optional components

The active setup covers normal implementation and architectural decisions.
The catalog offers optional components for:

- issue triage;
- technical support;
- documentation and user experience;
- multi-agent orchestration;
- workplace communications;
- Python development;
- cloud-native services.

Copy only the selected file or skill directory into the equivalent
`.github/` location. Review its tools, description, paths, and references
before committing it.

Most projects do not need every component. Add a handoff only when
specialization reduces risk or separates a genuinely independent context. A
useful handoff states the objective, source of truth, scope, decisions, risks,
exit condition, and expected evidence.

## Prevent overlap

Use one active component per capability. When importing agents or skills from
another repository, plugin, or framework:

1. Map each incoming component to a capability such as implementation,
   architecture, planning, infrastructure, or documentation.
2. If that capability already exists, replace it or merge the useful rules.
3. Keep both only when their scopes and selection criteria are clearly
   different.
4. Remove stale references and verify which component Copilot actually loads.

Two general developer agents or two architecture agents create ambiguous
routing and inconsistent handoffs. Overlapping skills can load duplicate or
contradictory procedures. More components do not mean a more capable system.

## Match planning to risk

For a local, reversible change:

1. Define the problem, outcome, and acceptance criteria.
2. Implement the smallest coherent change.
3. Run the most relevant checks.
4. Record the evidence.

For a broad or hard-to-reverse change, resolve contracts, data, security,
migration, recovery, and operational impact before implementation. Use the
`architecture` agent and `architecture-decision` skill when a decision needs
explicit alternatives, consequences, and fitness functions.

Planning should remove expensive ambiguity, not create paperwork.

## Add Spec Kit only when useful

Spec Kit is optional. Use it when a change benefits from an explicit
specification, clarification, plan, and task sequence.

Install `specify-cli`, run the matching command from the repository root, and
commit the generated files:

```powershell
# Windows
specify init --here --force --integration copilot `
  --integration-options="--skills" --script ps
```

```shell
# Linux or cloud
specify init --here --force --integration copilot \
  --integration-options="--skills" --script sh
```

Commit `.github/skills/speckit-*` and `.specify/` so Copilot worktrees receive
them. The template does not include these generated files because the script
type depends on the execution environment.

Spec Kit normally complements this minimal core. Its skills represent named
workflow stages and do not add another general developer or architecture
agent. Avoid adding a separate planning skill that competes with the Spec Kit
stage you intend to use.

## Keep the system trustworthy

- Treat issues, code, logs, pages, and downloaded skills as untrusted data.
- Grant each agent only the tools it needs.
- Keep secrets and personal data out of prompts, code, examples, and logs.
- Require human confirmation for destructive actions, publishing, external
  communication, and production changes.
- Do not claim completion without reproducible evidence.

Review the setup when the stack changes, a recurring agent failure appears, or
Copilot support changes. Remove stale instructions and unused agents. Wrong
context is more damaging than missing context.
