# Decision Log

- Date: 2026-04-21
- Title: Stevens Pass Neutral Secondary Remap
- Status: accepted
- Scope: brand color governance
- Brand (if brand-specific): Stevens Pass
- Figma file (if applicable): Foundations (`https://www.figma.com/design/70O01X6MWNKMpsLqIke99Q/Foundations`)
- Stakeholders: design_system_governance
- Supersedes: `figma/decisions/2026-03-18-stevens-pass-foundations-written-to-figma.md`
- Superseded by:

## Context

The repo still documented Stevens Pass as a three-family raw color model with `secondary_blue` driving the semantic `brand_secondary/*` lane.

The live Foundations file no longer matches that state. `_Global: Color` now includes `stevens_pass/neutral/*`, and the live semantic extension points the secondary expressive lane at `stevens_pass/neutral/*` instead of `secondary_blue/*`.

## Decision

Sync the repo to the live Figma state:

1. Record `stevens_pass/neutral/*` as a governed raw family in `_Global: Color`.
2. Keep `stevens_pass/stevens_blue/*` as the primary expressive semantic lane.
3. Record `stevens_pass/neutral/*` as the live source for `brand_secondary/*`.
4. Keep `secondary_blue` and `mossy_green` as governed raw families outside the current semantic secondary mapping.

## Scope

- Affected collections:
  - `_Global: Color`
  - `Semantic: Theme` extension `Stevens Pass`
- Affected tokens or artifact paths:
  - `stevens_pass/neutral/*`
  - `figma/brands/stevens_pass/color/intake.yml`
  - `figma/brands/stevens_pass/color/preview.md`
  - `figma/brands/stevens_pass/brand.yml`
- Explicit exceptions:
  - Shared semantic neutral tokens remain inherited from the base collection.
- Inherited or deferred items:
  - Stevens Pass typography governance remains unchanged.

## Consequences

The repo now reflects the live four-family Stevens Pass raw color inventory and the live semantic remap of `brand_secondary/*` to the neutral family.

## Follow-up

- Update:
  - Sync the Stevens Pass companion artifacts to the live color inventory and semantic alias state.
- Link from:
  - `figma/brands/stevens_pass/brand.yml`
- Verify:
  - `_Global: Color` contains `stevens_pass/neutral/100..900`
  - `color/surface/brand_secondary/default` resolves to `stevens_pass/neutral/900`
