# Decision Log

- Date: 2026-04-21
- Title: Liberty Mountain Live Color Realignment
- Status: accepted
- Scope: brand color governance
- Brand (if brand-specific): Liberty Mountain
- Figma file (if applicable): Foundations (`https://www.figma.com/design/70O01X6MWNKMpsLqIke99Q/Foundations`)
- Stakeholders: design_system_governance
- Supersedes: `figma/decisions/2026-03-30-liberty-mountain-ramp-consolidation.md`
- Superseded by:

## Context

The repo still documented Liberty Mountain as a nine-family raw color model with `sunrise` and `spring` driving the live expressive semantic lanes.

The live Foundations file no longer matches that state. `_Global: Color` now contains only five Liberty Mountain families: `cool_neutral`, `warm_neutral`, `shale`, `stone`, and `sunset`. The old `sunrise`, `spring`, `flora`, and `copper` families are no longer present in the live collection.

The live semantic extension also changed. Shared semantic neutral roles are inherited from the base collection, while the expressive brand lanes now resolve through `cool_neutral` and `warm_neutral`.

## Decision

Sync the repo to the live Figma state:

1. Record the live Liberty Mountain raw color inventory as five families:
   - `liberty_mountain/cool_neutral/*`
   - `liberty_mountain/warm_neutral/*`
   - `liberty_mountain/shale/*`
   - `liberty_mountain/stone/*`
   - `liberty_mountain/sunset/*`
2. Remove repo claims that `sunrise`, `spring`, `flora`, and `copper` are still live raw families.
3. Record the live semantic remap:
   - `brand/*` -> `liberty_mountain/cool_neutral/*`
   - `brand_secondary/*` -> `liberty_mountain/warm_neutral/*`
4. Keep the shared semantic neutral lane inherited from the base collection.

## Scope

- Affected collections:
  - `_Global: Color`
  - `Semantic: Theme` extension `Liberty Mountain`
- Affected tokens or artifact paths:
  - `figma/brands/liberty_mountain/color/intake.yml`
  - `figma/brands/liberty_mountain/color/preview.md`
  - `figma/brands/liberty_mountain/brand.yml`
- Explicit exceptions:
  - Shared semantic neutral tokens remain inherited from the base collection even though Liberty Mountain still carries raw warm and cool neutral families.
- Inherited or deferred items:
  - Liberty Mountain typography governance remains unchanged.

## Consequences

The repo now records the current live Liberty Mountain color structure and semantic lane mapping instead of preserving the earlier nine-family snapshot as if it were still active.

## Follow-up

- Update:
  - Sync the Liberty Mountain companion artifacts to the live color inventory and semantic alias state.
- Link from:
  - `figma/brands/liberty_mountain/brand.yml`
- Verify:
  - `_Global: Color` contains only five Liberty Mountain raw families
  - `color/surface/brand/default` resolves to `liberty_mountain/cool_neutral/700`
  - `color/surface/brand_secondary/default` resolves to `liberty_mountain/warm_neutral/300`
