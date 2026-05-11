# Decision Log

- Date: 2026-04-27
- Title: Epic standalone design system governance
- Status: Accepted
- Scope: Brand registry, brand manifest, and source intake provenance
- Brand (if brand-specific): Epic
- Figma file (if applicable): Foundations - Epic, https://www.figma.com/design/4Y5qG5CswdHwA0sdSGHCas/Foundations---Epic?node-id=1-4&p=f&t=Ppo6o9dyXoyzfpkN-11
- Stakeholders: design_system_governance
- Supersedes: None
- Superseded by:

## Context

Epic has its own standalone Foundations file and design system. It should be governed in this repository for provenance and operational clarity, but it should not be treated as another brand extension inside the shared Resorts Foundations file.

## Decision

Register Epic as an active brand with `design_system_scope: standalone`. The `Foundations - Epic` Figma file is the live source of truth for Epic global tokens. Epic is not modeled as a `Semantic: Theme` extension collection in the shared Resorts design system.

## Scope

- Affected collections: Epic collections in the standalone `Foundations - Epic` file: `_Global: Color`, `_Global: Typography`, `Global: Dimensions`, and `Semantic: Theme`.
- Affected tokens or artifact paths: `figma/brands/epic/brand.yml`, `figma/brands/epic/color/intake.yml`, `figma/brands/epic/typography/intake.yml`, `figma/brands/registry.yml`, `figma/brands/font-directory.md`, `figma/brands/font-inventory.yml`.
- Explicit exceptions: Epic does not follow the shared Resorts DS brand-extension route by default.
- Inherited or deferred items: Semantic/channel mapping remains deferred to a future explicit audit.

## Consequences

Epic governance can live beside the existing brand manifests without implying that Epic tokens belong in the shared Resorts file. Any future Epic Figma writes must target `Foundations - Epic` unless the user explicitly approves a migration or cross-system mapping.

## Follow-up

- Update: Epic semantic/channel mapping after an explicit audit is requested.
- Link from: `figma/brands/epic/brand.yml`.
- Verify: Confirm live Epic semantic and channel mappings before any downstream writes.
