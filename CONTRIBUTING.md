# Contributing to Istar Code Agent

Thanks for your interest in improving the Istar Code agent kernel!

## Ways to Contribute

1. **Report bugs** — Open an issue with reproduction steps.
2. **Suggest improvements** — Open an issue describing the enhancement.
3. **Submit PRs** — Fix bugs or refine the kernel.
4. **Improve docs** — Clarify the README or kernel wording.

## Getting Started

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/your-change`.
3. Make your changes:
   - Kernel: edit `agents/istar-code.md`, then copy it to `istar-code.md`
     at the repo root (identical content, no divergence).
   - Specialist/team agent: edit the single file under `agents/`.
   - Skill: edit `skills/istar-code-format/SKILL.md`.
4. Bump the `version` field in BOTH `istar-code.md` and
   `agents/istar-code.md` frontmatter and add a
   `CHANGELOG.md` entry when the kernel changes.
5. Run the banned-string check: no absolute paths, usernames, secrets,
   personal data, private topology, or hardcoded model IDs.
5. Commit using [Conventional Commits](https://www.conventionalcommits.org/):
   `type(scope): description`.
6. Push and open a Pull Request.

## Style Guide

- Keep the kernel deterministic and self-contained in `istar-code.md`.
- Use 2-space indentation for any YAML/JSON.
- Use LF line endings for all files.
- Avoid emojis in documentation files.
- Do not weaken the Safety Rules section.
- Update `CHANGELOG.md` with any user-facing change.

## Questions?

Open an issue on GitHub.

---

*End of CONTRIBUTING.md*
