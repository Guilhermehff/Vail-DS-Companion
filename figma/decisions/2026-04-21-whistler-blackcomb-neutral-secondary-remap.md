# Decision Log

- Date: 2026-04-21
- Title: Whistler Blackcomb Neutral Secondary Remap
- Status: accepted
- Scope: brand color governance
- Brand (if brand-specific): Whistler Blackcomb
- Figma file (if applicable): Foundations (`https://www.figma.com/design/70O01X6MWNKMpsLqIke99Q/Foundations`)
- Stakeholders: design_system_governance
- Supersedes:
- Superseded by:

## Context

The repo still documented Whistler Blackcomb as a one-family raw color model with `red/*` driving both expressive semantic lanes.

The live Foundations file now includes `whistler_blackcomb/neutral/*`, and the semantic extension points the secondary expressive lane at that neutral family instead of reusing `red/*`.

## Decision

Treat the live Figma state as canonical:

1. Record `whistler_blackcomb/neutral/*` as a governed raw family in `_Global: Color`.
2. Keep `whistler_blackcomb/red/*` as the primary expressive semantic lane.
3. Record `whistler_blackcomb/neutral/*` as the live source for `brand_secondary/*`.

## Scope

- Affected collections:
  - `_Global: Color`
  - `Semantic: Theme` extension `Whistler Blackcomb`
- Affected tokens or artifact paths:
  - `whistler_blackcomb/neutral/*`
  - `figma/brands/whistler_blackcomb/color/intake.yml`
  - `figma/brands/whistler_blackcomb/color/preview.md`
  - `figma/brands/whistler_blackcomb/brand.yml`
- Explicit exceptions:
  - Shared semantic neutral tokens remain inherited from the base collection.
- Inherited or deferred items:
  - Whistler Blackcomb typography governance remains unchanged.

## Consequences

The repo now reflects the live two-family Whistler Blackcomb raw color inventory and the live semantic remap of `brand_secondary/*` to the neutral family.

## Follow-up

- Update:
  - Sync the Whistler Blackcomb companion artifacts to the live color inventory and semantic alias state.
- Link from:
  - `figma/brands/whistler_blackcomb/brand.yml`
- Verify:
  - `_Global: Color` contains `whistler_blackcomb/neutral/100..900`
  - `color/surface/brand_secondary/default` resolves to `whistler_blackcomb/neutral/900`
