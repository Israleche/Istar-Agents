---
name: istar-code-format
description: "Apply a project's code format standards to generated code. Use BEFORE writing code when the project defines formatting references: match indentation, naming, comments, structure, and error-handling patterns from the project's example files. Triggers on 'format code', 'follow my standards', or 'match the example'."
---

# Code Format Skill (Portable Template)

## Purpose

All generated code MUST follow the formatting, style, structure, and patterns
defined in THIS project's reference examples. This skill is a portable
template: point it at your project's files, not at any fixed machine path.

## Step 0 — Bind the References (Required Once per Project)

Before first use, record the project's reference files in the project profile
(or `AGENTS.md`). Example bindings — replace with real repo-relative paths:

```text
style_guide:      docs/style-guide.md        # master formatting template
docs_standards:   docs/documentation.md      # doc/comment standards
text_encoding:    docs/text-encoding.md      # character/encoding rules
example_impl:     examples/real-world.impl   # real implementation example
example_folder:   examples/                  # additional concrete examples
agent_rules:      AGENTS.md                  # tool-scoped rules
```

Rules:

- Paths are REPO-RELATIVE. Never use absolute machine paths
  (`C:\…`, `/home/…`, drive letters, usernames).
- If a binding is missing, ask for it once, record it, then proceed.
- Never commit or log secrets found while reading references.

## Step 1 — Context Loading (Before Writing Code)

1. Read the style guide → base structure.
2. Read the documentation standards → presentation rules.
3. Read the text/encoding rules → character handling.
4. Read the real implementation example → practical pattern application.
5. Explore the examples folder when a specific pattern is needed.
6. Identify patterns common to ALL examples before writing anything.

## Step 2 — Pattern Extraction

Extract and apply:

- Naming conventions (variables, functions, files).
- Code organization and structure.
- Comment and documentation style.
- Formatting (indentation, spacing, line length).
- Error-handling patterns.
- Import and dependency organization.
- Header and footer conventions.
- Section ordering within files.

## Step 3 — Code Generation (Strict Adherence)

DO:

- Match indentation style from the examples exactly.
- Use the same comment format (language, symbols, placement).
- Follow variable naming patterns seen in the references.
- Replicate file header and structure conventions.
- Apply the same error-handling approach.
- Use identical spacing and blank-line patterns.
- Match bracket and brace style.
- Copy documentation format precisely.

DO NOT:

- Introduce naming conventions absent from the examples.
- Use different comment styles than the references.
- Change structural organization patterns.
- Add dependencies the project manifest does not declare.
- Weaken the project's safety rules to satisfy formatting.
