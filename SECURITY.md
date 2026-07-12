# Security Policy

## Supported Versions

This repository distributes the Istar Code agent kernel. We support the latest
released version (`v5.x`) with security-relevant fixes. Older releases are
provided as-is.

| Version | Supported |
|---------|-----------|
| 5.x     | ✅ Yes    |
| < 5.0   | ❌ No     |

## Reporting a Vulnerability

If you discover a security vulnerability (for example, a leaked credential, an
unsafe instruction in the kernel, or a privacy issue), **do not open a public
issue**.

Please report it privately using one of the following:

1. **GitHub Security Advisories** (preferred): open a private advisory from the
   repository's *Security → Report a vulnerability* tab.
2. A **confidential GitHub issue** if advisories are unavailable.

We aim to acknowledge reports within 72 hours and provide a remediation plan
within 7 days for confirmed issues.

## Configuration Safety

Before using the agent:

- Never commit API keys, tokens, or secrets. They are excluded via `.gitignore`.
- Review the `permissions` block in `istar-code.md` before enabling broad tool
  access (`bash: allow`, `edit: allow`).
- Keep safety rules intact — the kernel's Safety section is non-negotiable.

## Responsible Disclosure

We request that you give us a reasonable amount of time to address the issue
before any public disclosure.
