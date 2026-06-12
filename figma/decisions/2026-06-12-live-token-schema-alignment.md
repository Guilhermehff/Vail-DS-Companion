# Decision Log

- Date: 2026-06-12
- Title: Live token schema alignment
- Status: accepted
- Scope: Global token naming, Semantic Theme helper slots, Ads size paths, brand registry alignment
- Brand (if brand-specific): multiple active brands; Okemo added
- Figma file (if applicable): Foundations - Resorts
- Stakeholders: Design system governance, Foundations maintainers, channel library authors
- Supersedes:
  - figma/decisions/2026-03-17-semantic-color-assets-logo-brand-name-overrides.md for the asset selector path
  - figma/decisions/2026-04-06-semantic-theme-ad-typography-size-recipes.md for Ads path naming
  - figma/decisions/2026-04-06-semantic-theme-ad-brand-row-order-mappings.md for Ads profile naming
- Superseded by:

## Context

A live audit of `Foundations - Resorts` found that Figma had moved ahead of the repository in several places. The live file includes Okemo variables and a semantic extension, `_source` suffixes in raw color token names, `assets/brand` instead of the older logo asset path, profile-based Ads size tokens, written and numbered typography weight paths, semantic helper slots for subhead, letter case, accent-on-surface, component helpers, and approved non-numeric dimension primitives.

The repo needed to align with live Figma because Figma is the source of truth for current variables, collections, aliases, styles, components, and write state.

## Decision

1. Add Okemo to active repo governance and record its live Figma collection IDs in `figma/brands/okemo/brand.yml`.
2. Allow `_source` suffixes in live `_Global: Color` variable names when the suffix preserves the exact source swatch inside a 100-900 ramp.
3. Use `assets/brand` as the governed semantic brand selector path.
4. Use the live Ads raw size path `universal/size/ad/<role>/profile_<profile>/<slot>`.
5. Use the live Ads semantic size path `channel/ads/typography/size/<role>/<step>`.
6. Use `universal/weight/written/<key>` and `universal/weight/numbered/<number>` for raw typography weights.
7. Permit same-target semantic extension overrides when a brand needs explicit documented override state. Self-aliases remain invalid.
8. Admit the current live helper slots into active taxonomy, including:
   - `assets/image_corner`
   - `color/on_surface_accent/*`
   - `components/button/*`
   - `typography/family/subhead`
   - `typography/letter_case/*`
   - `channel/email/components/*`
   - `channel/ads/dimensions/image/padding/*`
9. Admit `space/null`, `radius/null`, and `radius/round` as approved non-numeric `Global: Dimensions` primitives.

## Scope

- Affected collections:
  - `_Global: Color`
  - `Global: Typography`
  - `Global: Dimensions`
  - `Semantic: Theme`
  - Semantic extension collection `Okemo`
- Affected tokens or artifact paths:
  - `figma/config/variable-taxonomy.yml`
  - `AGENTS.md`
  - `figma/docs/semantic-extension-write-workflow.md`
  - `prompts/figma/brand-extension-semantic-doc-pruning.md`
  - `figma/brands/registry.yml`
  - `figma/brands/okemo/brand.yml`
  - `figma/brands/*` current brand artifacts that referenced older asset or weight paths
- Explicit exceptions:
  - `_source` suffixes are allowed in live color token names only as source anchors within governed 100-900 ramps.
  - Same-target extension overrides are allowed when they represent intentional documentation or brand-state needs; self-aliases are still invalid.
  - The profile-based Ads size model remains channel-scoped and does not create a general semantic typography size system.
- Inherited or deferred items:
  - Historical decision logs may retain older token names when describing past state.
  - Okemo intake and preview artifacts remain deferred until source artifacts are available or explicitly requested.

## Consequences

Future audits should treat these live paths as canonical. Repo governance should no longer flag `_source` color anchors, profile-based Ads sizes, `assets/brand`, current weight namespaces, same-target documented overrides, or the listed helper slots as mismatches.

Okemo is now governed in the repo, but its local intake and preview artifacts are intentionally absent until source provenance is supplied or a local reconstruction is requested.

## Follow-up

- Update:
  - Use this decision as the active reference when pruning stale docs or writing future brand manifests.
- Link from:
  - Future decisions that expand channel-scoped semantic exceptions or component helper tokens.
- Verify:
  - Figma remains the source of truth for live collection IDs and override values.
  - Future audits distinguish historical decision text from active canonical documentation.
