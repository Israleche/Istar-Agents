# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [6.0.0] -- 2026-09-20

Public multi-agent release. The flagship `istar-code` kernel was sanitized for
public use, upgraded with current (2026) agent-engineering evidence, and
joined by a full `agents/` collection plus a portable format skill.

### Added

- `agents/` collection (19 files): flagship copy plus 9 `istar-*`
  specialists (`memory`, `pilot`, `search`, `read`, `context`, `think`,
  `vision`, `auto`, `tutor`) and 9 team subagents (`architect`, `debugger`,
  `reviewer`, `explorer`, `fixer`, `test-engineer`, `doc-writer`, `general`,
  `shipper`).
- `skills/istar-code-format/SKILL.md`: portable template binding
  repo-relative format references per project.
- `AGENTS.md`: public contributor conventions for this repository.
- Kernel Section 4 (context surfaces), checkpoint injection, retrieval
  budgeting, error-context preservation, spec-first out-of-scope rule,
  instruction-vs-guidance rule, and Task Self-Check — backed by 2026 context
  engineering literature (Anthropic context engineering, LangChain
  Write-Select-Compress-Isolate, "lost in the middle" ordering, KV-cache
  prefix stability) and SWE-bench scaffold findings (scaffold moves results
  5–30 points; verification and tool design outweigh model choice).

### Changed

- Kernel version 5.0.0 → 6.0.0. Verification hierarchy standardized to
  V1 syntax / V2 lint / V3 tests / V4 typecheck / V5 build-run / V6 smoke,
  minimum V1+V3.
- `README.md` rewritten as a multi-agent catalog with OpenCode-first install.
- `CONTRIBUTING.md` updated for the `agents/` + `skills/` layout.

### Removed (privacy sanitization — breaking for private forks)

- Absolute machine paths, drive roots, usernames, and personal workspace
  layouts (including school, credential-manager, and network-topology details).
- Hardcoded model identifiers and provider-specific fallback chains; no model
  is pinned — the host's global/invoker model applies unless overridden.
- Personal tutor profiles and grades; replaced by a generic configurable
  `istar-tutor` template with no personal data built in.
- Environment-specific integrations (private MCP servers, local config paths,
  host-specific startup sequences); replaced by portable capability notes.

---

## [Unreleased]

### Added

- Repository health files: `SECURITY.md`, `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`,
  GitHub issue templates (bug report, feature request) and `PULL_REQUEST_TEMPLATE.md`.
- `assets/logo.png` brand logo.
- Refined `.gitignore` (dependencies, build/cache output, secrets, editor noise).

### Changed

- Split the kernel out of `README.md` into a dedicated, copy-ready
  [`istar-code.md`](istar-code.md) (the agent file). `README.md` is now a project
  overview with install instructions and badges.
- Fixed kernel frontmatter: `author` → `Istar Code Team`,
  `repository` → `github.com/Israleche/istar-code-agent`.

---

## [5.0.0] -- 2026-07-12

### Added

- Standalone distribution of the Istar Code v5.0.0 deterministic kernel.
- 16-section specification: instruction hierarchy, execution cycle with phase
  gates, task classification (T1–T6), tool hierarchy with mandatory batching,
  context budgeting with auto-compression, verification hierarchy (V1–V6),
  structured memory system, skill lifecycle, post-task reflection, and safety
  rules.
