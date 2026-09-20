# AGENTS.md — Contributor Conventions for `istar-code-agent`

Instructions for AI agents and humans working in THIS repository.

## Scope

- Kernel changes: edit `agents/istar-code.md`, then sync the copy-ready
  distribution file: copy it to `istar-code.md` at the repo root (identical
  content, no divergence).
- Specialist/team changes: edit the single file under `agents/`.
- Skill changes: edit `skills/istar-code-format/SKILL.md`.
- Every code/config/agent change updates `CHANGELOG.md` in the SAME iteration.

## Rules

1. English only in all committed files.
2. No absolute machine paths, usernames, personal data, secrets, credentials,
   or environment-specific topology (drives, ports, hosts, internal meshes).
3. No hardcoded model identifiers. Agents are model-agnostic: omit `model`
   so the host global/invoker model applies; document overrides in `README.md`.
4. Portable frontmatter only: `description` (required, routing signal),
   `mode` (`primary` / `subagent` / `all`), `permissions` with
   `allow` / `ask` / `deny`. Keep `temperature` out unless the agent's
   determinism genuinely requires it.
5. Determinism first: numbered procedures, decision tables, return contracts
   with word limits, `path:line` evidence, explicit verification per step.
6. Tables over prose; diffs over full-file dumps.
7. Safety rules are non-negotiable: archive over delete, ask before
   destructive actions, never commit secrets.
8. Conventional Commits (`type(scope): subject`, max 72 chars, imperative).
   One commit per coherent logical change.
9. Verify before reporting done: files parse (frontmatter valid), no banned
   strings (see below), repo tree matches `README.md` layout.

## Banned-String Check (run before every commit)

No committed file may contain: absolute Windows paths (`C:\`, `S:\`),
usernames or personal identifiers, credential-manager references, private
hostnames/ports/mesh details, hardcoded provider model IDs, or personal
academic records. Grep for these before committing.

## Versioning

- Kernel edits bump `version` in BOTH `istar-code.md` and
  `agents/istar-code.md` frontmatter plus a `CHANGELOG.md` entry.
- Non-kernel agent/skill edits get a `CHANGELOG.md` entry under
  `[Unreleased]` (or a minor bump for a release).
