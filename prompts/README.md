# Prompts

Reusable prompts for Vail Resorts Design System companion workflows.

Prompts in this folder should support repeatable governance tasks such as brand intake, Figma audits, semantic extension planning, email component review, and repository cleanup. They should not duplicate live Figma state, token inventories, component specs, or canonical governance rules.

Canonical governance remains in:

- `AGENTS.md`
- `figma/config/variable-taxonomy.yml`
- `figma/brands/registry.yml`
- accepted decision logs in `figma/decisions/`

## Structure

- `figma/`: prompts for Figma MCP workflows, variable governance, brand foundations, and channel-library work.
- `repo/`: prompts for repository maintenance, documentation cleanup, and governance artifact review.

## Naming

- Use lowercase, hyphenated Markdown filenames.
- Name prompts by repeatable workflow, not by date.
- Prefer `brand-intake.md` over `2026-06-12-brand-intake.md`.

## Prompt Format

Each prompt should include:

- Purpose
- When to use
- Prompt text
- Required context or source files
- Expected output

If a prompt depends on governance rules, reference the canonical file instead of copying the rule text.
