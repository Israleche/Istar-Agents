<p align="center"><img src="assets/logo.png" alt="Istar Code Logo" width="200"/></p>

<h1 align="center">Istar Code Agent</h1>

<p align="center">
  <a href="https://github.com/Israleche/istar-code-agent/releases"><img alt="Release" src="https://img.shields.io/github/v/release/Israleche/istar-code-agent?label=release&color=blue"></a>
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-green.svg"></a>
  <a href="https://github.com/Israleche/istar-code-agent/issues"><img alt="Issues" src="https://img.shields.io/github/issues/Israleche/istar-code-agent"></a>
  <a href="CONTRIBUTING.md"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
</p>

<p align="center">
<strong>The standalone, distribution-ready Istar Code agent kernel (v5.0.0).</strong><br/>
A deterministic, model-agnostic autonomous coding agent — identical behavior from 1B to 500B parameters.
</p>

---

## What is this?

`istar-code-agent` is the **single-file distribution** of the Istar Code agent
kernel. It contains the complete, self-contained agent definition that you can
drop into any agent-compatible environment (Kilo Code, GitHub Copilot Chat, or
any tool that loads a Markdown agent prompt).

The agent file is [`istar-code.md`](istar-code.md) — copy it as-is, no build step
required.

## Features

- **Deterministic execution** — `INSPECT > PLAN > EXECUTE > VERIFY > REFLECT` with
  explicit phase gates and a two-failure stop rule.
- **Instruction hierarchy** — safety rules always win over conventions, user
  instructions, skills, and defaults.
- **Task classification & routing** — six task classes (T1–T6) with a routing
  decision table.
- **Context budgeting** — 50–60% task / 20–25% loaded / 10–15% memory with
  auto-compression and progressive disclosure.
- **Verification-first** — a V1–V6 verification hierarchy with a minimum bar
  before any success is reported.
- **Structured memory** — six capped memory files with write gates.
- **Skill lifecycle** — candidate → proposed → active → deprecated → archived.
- **Safety by default** — archive over delete, ask before destructive actions,
  never commit secrets.

See [`istar-code.md`](istar-code.md) for the full, authoritative specification.

## Install

### Kilo Code

```powershell
# Copy the agent into your Kilo agents directory
Copy-Item ".\istar-code.md" "$env:USERPROFILE\.config\kilo\agents\istar-code.md" -Force
```

Reload VS Code (`Ctrl+Shift+P` → *Developer: Reload Window*). Invoke the agent by
name in chat.

### GitHub Copilot Chat (BYOK)

Register the agent in your VS Code `settings.json`:

```json
"github.copilot.chat.agents": {
  "istar-code": {
    "name": "Istar Code",
    "description": "Deterministic, model-agnostic coding agent (v5.0.0 kernel)",
    "instructionsFile": "${workspaceFolder}/istar-code.md",
    "tools": ["codebase", "changes", "problems"]
  }
}
```

Type `@istar-code` in Copilot Chat to invoke it.

## Repository Layout

```
istar-code-agent/
├── istar-code.md       # The agent kernel (v5.0.0) — copy-ready, self-contained
├── assets/logo.png     # Brand logo
├── CHANGELOG.md        # Version history
├── CONTRIBUTING.md     # Contribution guidelines
├── SECURITY.md         # Vulnerability disclosure policy
├── CODE_OF_CONDUCT.md  # Contributor Covenant
├── LICENSE             # MIT
└── README.md           # This file
```

## Versioning

This project follows [Semantic Versioning](https://semver.org/). The agent
kernel version is declared in the `version` field of the
[`istar-code.md`](istar-code.md) frontmatter and mirrored in release tags
(`v5.0.0`, …). See [`CHANGELOG.md`](CHANGELOG.md).

## Contributing

PRs and issues are welcome. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) first and
use [Conventional Commits](https://www.conventionalcommits.org/).

## Security

Found a vulnerability? **Do not open a public issue.** See
[`SECURITY.md`](SECURITY.md) for private disclosure via GitHub Security
Advisories.

## License

[MIT](LICENSE) © Istar Code Team.
