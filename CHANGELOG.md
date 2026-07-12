# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
