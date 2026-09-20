<p align="center"><img src="assets/logo.png" alt="Istar Agents Logo" width="200"/></p>

<h1 align="center">Istar Agents</h1>

<p align="center">
  <a href="https://github.com/Israleche/Istar-Agents/releases"><img alt="Release" src="https://img.shields.io/github/v/release/Israleche/Istar-Agents?label=release&color=blue"></a>
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-green.svg"></a>
  <a href="https://github.com/Israleche/Istar-Agents/issues"><img alt="Issues" src="https://img.shields.io/github/issues/Israleche/Istar-Agents"></a>
  <a href="CONTRIBUTING.md"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
</p>

<p align="center">
<strong>Deterministic, model-agnostic autonomous coding agents (v6.0.0).</strong><br/>
Same behavior on small local models and frontier APIs — the scaffold carries the quality, not the model.
</p>

---

## Quickstart (30 Seconds)

```powershell
# 1. Copy the flagship agent into OpenCode (global, all projects)
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\opencode\agents\istar-code.md" -Force
```

```json
// 2. Make it the default in opencode.json
{ "$schema": "https://opencode.ai/config.json", "default_agent": "istar-code" }
```

Done. `istar-code` now runs every session. Add the rest of `agents/` whenever
you want specialists and a review team. Details in [Install](#install).

## What Is This?

A public, distribution-ready collection of agent definitions. Each file is
self-contained Markdown with portable frontmatter — drop it into any
agent-compatible environment, no build step required.

### Flagship

| Agent | File | Role |
|-------|------|------|
| **Istar Code** (primary) | `istar-code.md` (= `agents/istar-code.md`) | Autonomous coding: web-first, exact scope, V1–V6 verification, delegation, memory |

### Specialists (`istar-*`)

| Agent | File | Role |
|-------|------|------|
| istar-memory | `agents/istar-memory.md` | Structured markdown memory + optional retrieval, strict write gates |
| istar-pilot | `agents/istar-pilot.md` | System operator: files, shell, services with safe defaults |
| istar-search | `agents/istar-search.md` | Web-first researcher with cited sources |
| istar-read | `agents/istar-read.md` | Deep reader for docs, repos, long pages |
| istar-context | `agents/istar-context.md` | Library-docs specialist (current API per installed version) |
| istar-think | `agents/istar-think.md` | Deep reasoner: options, decision, verifiable plan (no code) |
| istar-vision | `agents/istar-vision.md` | Screenshot, UI, diagram, and chart analyst |
| istar-auto | `agents/istar-auto.md` | Browser verification and web smoke tests |
| istar-tutor | `agents/istar-tutor.md` | Evidence-based study tutor (configure per course) |

### Team (code review pipeline)

| Agent | File | Role |
|-------|------|------|
| architect | `agents/architect.md` | System design + plan, no implementation |
| debugger | `agents/debugger.md` | Reproduce, isolate, diagnose — no fixes |
| reviewer | `agents/reviewer.md` | Strict review with severity + verdict, no edits |
| explorer | `agents/explorer.md` | Fast read-only codebase mapping |
| fixer | `agents/fixer.md` | Mechanical lint/typecheck/format fixes |
| test-engineer | `agents/test-engineer.md` | TDD tests: unit, integration, characterization |
| doc-writer | `agents/doc-writer.md` | Docs only, never implementation |
| general | `agents/general.md` | Self-contained multi-step executor |
| shipper | `agents/shipper.md` | Release prep; never pushes without confirmation |

### Skills

| Skill | Path | Role |
|-------|------|------|
| istar-code-format | `skills/istar-code-format/SKILL.md` | Portable template binding a project's format references (repo-relative paths) |

See [`istar-code.md`](istar-code.md) for the full flagship specification and
[`AGENTS.md`](AGENTS.md) for contributor conventions.

## Why These Agents?

- **Deterministic execution** — `INSPECT > PLAN > EXECUTE > VERIFY > REFLECT`
  with explicit phase gates and attempt limits. No vibes, no skipped steps.
- **Instruction hierarchy** — safety beats conventions beats user instructions
  beats skills beats defaults. Conflicts resolve by number, not by mood.
- **Web-first** — search current sources before asserting; cite; mark
  unverified claims. Training data goes stale, the web wins.
- **Exact scope** — do what was asked, nothing more, nothing less, with an
  explicit out-of-scope statement per task.
- **Verification-first** — V1 syntax → V2 lint → V3 tests → V4 typecheck →
  V5 build/run → V6 smoke test. Minimum V1+V3 before any success is reported.
- **Context engineering** — the right information on the right surface
  (kernel, project rules, skills, subagents, memory, task spec); progressive
  disclosure; retrieval budgeting; checkpoint injection on long tasks.
- **Model-agnostic** — no model is pinned in any file. The primary agent uses
  your globally configured model; subagents inherit the invoker's model
  unless you override it.
- **Safety by default** — archive over delete, ask before destructive
  actions, never commit secrets or personal data.

## Requirements

- A host that loads Markdown agents: [OpenCode](https://opencode.ai/docs/agents/)
  (primary target), Kilo Code, GitHub Copilot Chat, or any tool that accepts a
  Markdown system prompt.
- No dependencies, no build, no API keys. Optional capabilities (web search,
  browser automation, vector retrieval) are used when the host provides them
  and skipped gracefully when it does not.

## Install

### OpenCode

```powershell
# Full collection, global (all projects)
Copy-Item ".\agents\*.md" "$env:USERPROFILE\.config\opencode\agents\" -Force

# Full collection, per-project
Copy-Item ".\agents\*.md" ".\.opencode\agents\" -Force

# Flagship only
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\opencode\agents\istar-code.md" -Force
```

Set the default agent in `opencode.json`:

```json
{ "$schema": "https://opencode.ai/config.json", "default_agent": "istar-code" }
```

Notes:

- The file name becomes the agent ID (`istar-code.md` → `istar-code`).
- `mode: primary` agents run sessions; `mode: subagent` agents run as child
  sessions; `mode: all` can do both.
- Older setups may use the singular `agent/` folder — both spellings are
  accepted for backwards compatibility.
- See the [OpenCode agents guide](https://opencode.ai/docs/agents/) for
  per-agent `model`, `temperature`, `steps`, and `permission` overrides.

### Kilo Code

```powershell
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\kilo\agents\istar-code.md" -Force
```

Reload the window (`Ctrl+Shift+P` → *Developer: Reload Window*), then invoke
the agent by name in chat.

### GitHub Copilot Chat

Register the agent in VS Code `settings.json`:

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

Type `@istar-code` in Copilot Chat to invoke it.

## Repository Layout

```text
Istar-Agents/
├── istar-code.md                 # Flagship kernel (copy-ready, self-contained)
├── agents/                       # All agents (flagship copy + specialists + team)
│   ├── istar-code.md             # (identical to ../istar-code.md — keep in sync)
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
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
├── assets/logo.png
├── AGENTS.md                     # Contributor conventions (for humans and AI agents)
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── LICENSE
└── README.md
```

## Versioning

[Semantic Versioning](https://semver.org/). The kernel version lives in the
`version` field of the `istar-code.md` frontmatter and is mirrored in release
tags (`v6.0.0`, …) and [GitHub Releases](https://github.com/Israleche/Istar-Agents/releases).
See [`CHANGELOG.md`](CHANGELOG.md).

## Contributing

PRs and issues are welcome. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) first
(kernel edits touch `agents/istar-code.md` + the root copy + `CHANGELOG.md`)
and use [Conventional Commits](https://www.conventionalcommits.org/).

## Security

Found a vulnerability? **Do not open a public issue.** See
[`SECURITY.md`](SECURITY.md) for private disclosure via GitHub Security
Advisories.

## License

[MIT](LICENSE) © Istar Code Team.
