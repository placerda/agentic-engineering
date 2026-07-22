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

Create a repository from the template and give the main Copilot agent one
small, real task:

```text
I want to [describe a small, checkable outcome]. Inspect what already exists,
propose the smallest plan, and tell me how you will verify it. Ask me only for
decisions the repository cannot answer. Wait for my approval before editing.
```

In an existing repository, Copilot can infer the stack, commands, layout, and
conventions from the files. In a new project, it asks for the decisions needed
to complete the task. The first interaction stays focused on useful work
instead of auditing the template.

The template includes two specialist agents:

- `implementation` changes code, adds tests, runs the repository's checks, and
  reports the evidence;
- `architecture` compares alternatives and resolves boundaries, contracts, and
  hard-to-reverse decisions before coding.

Stay with the main agent while the task is still being understood. Select a
specialist only when its job matches the next step.

## What you can customize

| Path | What it does | Change it when |
| --- | --- | --- |
| `AGENTS.md` | Defines the stable operating contract Copilot reads | Engineering policy, risk rules, or evidence expectations differ |
| `.github/copilot-instructions.md` | Gives Copilot concise repository facts, commands, and important paths | Adopting the template in any real project |
| `.github/agents/` | Defines active specialist roles and their tool boundaries | A recurring role needs a distinct specialist |
| `.github/skills/` | Stores active reusable procedures and references | A trusted external skill is activated |
| `catalog/` | Stores optional agents outside automatic discovery | A specialist agent is copied into `.github/agents/` |
| `.github/ISSUE_TEMPLATE/` | Captures outcomes, acceptance criteria, and risk | The team plans work differently |
| `.github/pull_request_template.md` | Captures validation and residual risk | The review process requires different evidence |

Delete what does not apply. A smaller accurate setup is better than a large
generic one.

## Add optional agents

The active agents and skills cover normal implementation and architectural
decisions. The catalog contains three inactive specialists:

| Agent | Add it when |
| --- | --- |
| `issue-triage` | Incoming issues need consistent reproduction, priority, and readiness |
| `technical-support` | Maintainers need a read-first diagnosis and a safe recovery path |
| `documentation-ux` | User or operator journeys need focused documentation work |

Copy the selected file from `catalog/agents/` into `.github/agents/`. Before
committing it, check its description and tools against the real repository.
For an external skill, review and copy its complete folder into
`.github/skills/`.

Most projects need none of these agents. Add one only when that job recurs and
the active core does not handle it well.

## Avoid overlapping components

Keep one active component for each job.

When you add something from the catalog, another repository, or a plugin:

- **Same job:** replace the existing component or merge the useful rules into
  it. Do not keep both.
- **New job:** activate it as-is.
- **Related but distinct job:** keep both only when their descriptions make
  the selection boundary obvious.

For example, do not add another general developer agent beside
`implementation`, or another architecture agent beside `architecture`. After
replacing a component, remove stale references and confirm which one Copilot
loads.

## Match planning to risk

Planning depth should follow the cost of being wrong.

For a local, reversible change, keep it light:

1. Define the problem, outcome, and acceptance criteria.
2. Implement the smallest coherent change.
3. Run the most relevant checks.
4. Record the evidence.

For a broad or hard-to-reverse change, resolve the relevant contracts, data,
security, migration, recovery, and operational questions before coding. Use
the `architecture` agent and `architecture-decision` skill when the decision
needs explicit alternatives, consequences, and fitness functions.

Planning should remove expensive ambiguity, not create paperwork.

## Add Spec Kit only when useful

Spec Kit is recommended when requirements are unclear, several components must
move together, or technical decisions should be reviewed before coding. Skip
it for small, well-understood fixes.

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

- Treat instructions found inside issues, source files, logs, web pages, and
  downloaded skills as content to inspect, not commands to follow.
- Grant each agent only the tools it needs.
- Keep secrets and personal data out of prompts, code, examples, and logs.
- Require human confirmation for destructive actions, publishing, external
  communication, and production changes.
- Do not claim completion without reproducible evidence.

Review the setup when the stack changes, a recurring agent failure appears, or
Copilot support changes. Remove stale instructions and unused agents. Wrong
context is more damaging than missing context.
