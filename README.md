<p align="center"><img src="assets/logo.png" alt="Istar Code Logo" width="200"/></p>

<h1 align="center">Istar Code Agents</h1>

<p align="center">
  <a href="https://github.com/Israleche/istar-code-agent/releases"><img alt="Release" src="https://img.shields.io/github/v/release/Israleche/istar-code-agent?label=release&color=blue"></a>
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-green.svg"></a>
  <a href="https://github.com/Israleche/istar-code-agent/issues"><img alt="Issues" src="https://img.shields.io/github/issues/Israleche/istar-code-agent"></a>
  <a href="CONTRIBUTING.md"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
</p>

<p align="center">
<strong>Deterministic, model-agnostic autonomous coding agents (v6.0.0).</strong><br/>
Identical behavior across model capacities — from small local models to frontier APIs.
</p>

---

## What Is This?

A public, distribution-ready collection of agent definitions. Drop any file
into an agent-compatible environment — no build step required.

| Agent | File | Role |
|-------|------|------|
| **Istar Code** (flagship, primary) | `istar-code.md` / `agents/istar-code.md` | Autonomous vibe-coding: web-first, exact scope, V1–V6 verification, delegation, memory |
| istar-memory | `agents/istar-memory.md` | Structured markdown memory + optional retrieval, strict write gates |
| istar-pilot | `agents/istar-pilot.md` | System operator: files, shell, services with safe defaults |
| istar-search | `agents/istar-search.md` | Web-first researcher with cited sources |
| istar-read | `agents/istar-read.md` | Deep reader for docs, repos, long pages |
| istar-context | `agents/istar-context.md` | Library-docs specialist (current API per installed version) |
| istar-think | `agents/istar-think.md` | Deep reasoner: options, decision, verifiable plan (no code) |
| istar-vision | `agents/istar-vision.md` | Screenshot, UI, diagram, and chart analyst |
| istar-auto | `agents/istar-auto.md` | Browser verification and web smoke tests |
| istar-tutor | `agents/istar-tutor.md` | Evidence-based study tutor (configure per course) |
| architect | `agents/architect.md` | System design + plan, no implementation |
| debugger | `agents/debugger.md` | Reproduce, isolate, diagnose — no fixes |
| reviewer | `agents/reviewer.md` | Strict review with severity + verdict, no edits |
| explorer | `agents/explorer.md` | Fast read-only codebase mapping |
| fixer | `agents/fixer.md` | Mechanical lint/typecheck/format fixes |
| test-engineer | `agents/test-engineer.md` | TDD tests: unit, integration, characterization |
| doc-writer | `agents/doc-writer.md` | Docs only, never implementation |
| general | `agents/general.md` | Self-contained multi-step executor |
| shipper | `agents/shipper.md` | Release prep; never pushes without confirmation |

Skills:

| Skill | Path | Role |
|-------|------|------|
| istar-code-format | `skills/istar-code-format/SKILL.md` | Portable template binding a project's format references (repo-relative paths) |

See `istar-code.md` for the full flagship specification and `AGENTS.md` for
contributor conventions.

## Design Principles

- **Deterministic execution** — `INSPECT > PLAN > EXECUTE > VERIFY > REFLECT`
  with explicit phase gates and attempt limits.
- **Instruction hierarchy** — safety wins over conventions, user instructions,
  skills, and defaults, in that order.
- **Web-first** — search current sources before asserting; cite; mark
  unverified claims.
- **Exact scope** — do what was asked, nothing more, nothing less, with an
  explicit out-of-scope statement.
- **Verification-first** — V1–V6 hierarchy with a minimum bar before any
  success is reported.
- **Context engineering** — right information on the right surface (kernel,
  project rules, skills, subagents, memory, task spec); progressive
  disclosure; retrieval budgeting; checkpoint injection.
- **Model-agnostic** — no model is pinned. The primary agent uses the global
  model; subagents inherit the invoker's model unless overridden.
- **Safety by default** — archive over delete, ask before destructive
  actions, never commit secrets or personal data.

## Install

### OpenCode (recommended layout)

```powershell
# Global install (all projects)
Copy-Item ".\agents\*.md" "$env:USERPROFILE\.config\opencode\agents\" -Force
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\opencode\agents\istar-code.md" -Force

# Per-project install
Copy-Item ".\agents\*.md" ".\.opencode\agents\" -Force
```

Set the default agent in `opencode.json`:

```json
{ "$schema": "https://opencode.ai/config.json", "default_agent": "istar-code" }
```

The file name becomes the agent ID (`agents/istar-code.md` → `istar-code`).
`mode: primary` agents run sessions; `mode: subagent` agents run as child
sessions; `mode: all` can do both. See the
[OpenCode agents guide](https://opencode.ai/docs/agents/) for `model`,
`temperature`, `steps`, and `permission` overrides.

### Kilo Code

```powershell
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\kilo\agents\istar-code.md" -Force
```

Reload the window, then invoke the agent by name in chat.

### GitHub Copilot Chat

```json
"github.copilot.chat.agents": {
  "istar-code": {
    "name": "Istar Code",
    "description": "Deterministic, model-agnostic coding agent (v6 kernel)",
    "instructionsFile": "${workspaceFolder}/istar-code.md",
    "tools": ["codebase", "changes", "problems"]
  }
}
```

## Repository Layout

```text
istar-code-agent/
├── istar-code.md                 # Flagship kernel (copy-ready, self-contained)
├── agents/                       # All agents (flagship copy + specialists + team)
│   ├── istar-code.md
│   ├── istar-memory.md
│   ├── istar-pilot.md
│   ├── istar-search.md
│   ├── istar-read.md
│   ├── istar-context.md
│   ├── istar-think.md
│   ├── istar-vision.md
│   ├── istar-auto.md
│   ├── istar-tutor.md
│   ├── architect.md
│   ├── debugger.md
│   ├── reviewer.md
│   ├── explorer.md
│   ├── fixer.md
│   ├── test-engineer.md
│   ├── doc-writer.md
│   ├── general.md
│   └── shipper.md
├── skills/
│   └── istar-code-format/SKILL.md
├── assets/logo.png
├── AGENTS.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── LICENSE
└── README.md
```

## Versioning

[Semantic Versioning](https://semver.org/). The kernel version is declared in
the `version` field of the `istar-code.md` frontmatter and mirrored in release
tags (`v6.0.0`, …). See [`CHANGELOG.md`](CHANGELOG.md).

## Contributing

PRs and issues are welcome. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) first
and use [Conventional Commits](https://www.conventionalcommits.org/).

## Security

Found a vulnerability? **Do not open a public issue.** See
[`SECURITY.md`](SECURITY.md) for private disclosure via GitHub Security
Advisories.

## License

[MIT](LICENSE) © Istar Code Team.
