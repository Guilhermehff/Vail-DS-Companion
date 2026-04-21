# Decision Log

- Date: 2026-04-21
- Title: Boston Mills Neutral Source Anchor Shift
- Status: accepted
- Scope: brand color governance
- Brand (if brand-specific): Boston Mills / Brandywine
- Figma file (if applicable): Foundations (`https://www.figma.com/design/70O01X6MWNKMpsLqIke99Q/Foundations`)
- Stakeholders: design_system_governance, brand foundations review
- Supersedes:
- Superseded by:

## Context

Boston Mills / Brandywine was previously documented in the repo as a black-only brand with no raw color family in `_Global: Color`.

The live Foundations file no longer matches that repo state. A Boston Mills neutral ramp was added in `_Global: Color`, the source anchor moved to `Snowgun Grey` at `boston_mills/neutral/700`, exact black was preserved at `boston_mills/neutral/900`, and the surrounding steps were adjusted into a continuous 100-900 neutral ladder.

The live semantic extension also changed with that raw update. The expressive `brand` and `brand_secondary` lanes now resolve through `boston_mills/neutral/*` instead of directly using `universal/black`.

## Decision

Treat the live Figma state as canonical and sync the repo to that model.

Record Boston Mills / Brandywine as carrying one raw global color family, `boston_mills/neutral/*`, with these governed anchor rules:

- `boston_mills/neutral/700` preserves `Snowgun Grey` (`#474E50`)
- `boston_mills/neutral/900` preserves exact black (`#000000`)

Keep the shared semantic neutral role set inherited from the base collection, but record the expressive semantic brand lanes as Boston Mills neutral aliases:

- `color/surface/brand/default` -> `boston_mills/neutral/700`
- `color/surface/brand/strong` -> `boston_mills/neutral/800`
- `color/surface/brand_secondary/default` -> `boston_mills/neutral/700`
- `color/foreground/brand` -> `boston_mills/neutral/700`
- `color/border/brand` -> `boston_mills/neutral/400`
- `color/on_surface/brand/*` stays contrast-derived from `universal/white`

## Scope

- Affected collections:
  - `_Global: Color`
  - `Semantic: Theme` extension `Boston Mills / Brandywine`
- Affected tokens or artifact paths:
  - `boston_mills/neutral/*`
  - `figma/brands/boston_mills_brandywine/color/intake.yml`
  - `figma/brands/boston_mills_brandywine/color/preview.md`
  - `figma/brands/boston_mills_brandywine/brand.yml`
- Explicit exceptions:
  - Shared semantic neutral tokens remain inherited from the base collection instead of re-pointing them into the Boston Mills raw neutral family.
- Inherited or deferred items:
  - Boston Mills typography governance remains unchanged.
  - Channel-library follow-up remains deferred.

## Consequences

The repo now needs to treat Boston Mills / Brandywine as a brand with one governed raw neutral family rather than as a black-only exception with no raw color family.

This keeps the companion artifacts aligned to the current Global Tokens documentation and the live semantic extension behavior in Figma. It also preserves the rationale for why Snowgun Grey, not black, is the primary source anchor on-ramp.

## Follow-up

- Update:
  - Sync Boston Mills companion artifacts to the live raw ramp and semantic alias state.
- Link from:
  - `figma/brands/boston_mills_brandywine/brand.yml`
- Verify:
  - `_Global: Color` contains `boston_mills/neutral/100..900`
  - `boston_mills/neutral/700` resolves to `#474E50`
  - `boston_mills/neutral/900` resolves to `#000000`
  - The Boston Mills semantic extension points default expressive brand surfaces at `boston_mills/neutral/700`
