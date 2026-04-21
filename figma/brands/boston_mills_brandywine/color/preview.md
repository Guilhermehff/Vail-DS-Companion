# Boston Mills / Brandywine Color Preview

Review state: written in figma. Verify live write state in `figma/brands/boston_mills_brandywine/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Snowgun Grey`
  Provided value: `#474e50`
- Source color: `Black`
  Provided value: `#000000`

## Universal Reuse

- Source color: `Black`
  Proposed token: `universal/black`
  Notes: Exact match.

## Live Raw Family

- Raw family: `boston_mills/neutral/*`
  Notes: `neutral/700` preserves `Snowgun Grey` and `neutral/900` preserves exact black.

## Live Semantic Mapping

- Scope: `neutral` -> `inherited_base`
  Exact black and white remain inherited from the shared neutral baseline.
- Scope: `brand` -> `boston_mills/neutral`
  The live semantic brand lane now resolves through the Boston Mills neutral family, with `boston_mills/neutral/700` as the default expressive source and `neutral/800` on the stronger surfaces.
- Scope: `brand_secondary` -> `boston_mills/neutral`
  The live secondary expressive lane follows the same neutral family.
- Scope: `border/brand` -> `boston_mills/neutral/400`
  The brand border lane is no longer treated as shared black.
- Scope: `on_surface/brand/*` -> `universal/white`
  Contrast text remains shared and is not hue-tinted.
- `variables/assets/logo` -> `Boston Mills / Brandywine`

## Review Readiness

- Subject: `Boston Mills / Brandywine neutral ramp shift`
  Rule: Keep `Snowgun Grey` anchored at `boston_mills/neutral/700`, preserve exact black at `boston_mills/neutral/900`, and use the neutral family for both expressive semantic lanes.
