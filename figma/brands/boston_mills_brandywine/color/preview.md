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

## Proposed Families

### Family: neutral

Source anchors: `700_source / 900_source`

<div>
  <span title="100 #f5f7f7" style="display:inline-block;width:32px;height:32px;background:#f5f7f7;border:1px solid #d1d5db;"></span>
  <span title="200 #e3e7e8" style="display:inline-block;width:32px;height:32px;background:#e3e7e8;border:1px solid #d1d5db;"></span>
  <span title="300 #c7ced1" style="display:inline-block;width:32px;height:32px;background:#c7ced1;border:1px solid #d1d5db;"></span>
  <span title="400 #a6b0b4" style="display:inline-block;width:32px;height:32px;background:#a6b0b4;border:1px solid #d1d5db;"></span>
  <span title="500 #828e93" style="display:inline-block;width:32px;height:32px;background:#828e93;border:1px solid #d1d5db;"></span>
  <span title="600 #657379" style="display:inline-block;width:32px;height:32px;background:#657379;border:1px solid #d1d5db;"></span>
  <span title="700 #474e50" style="display:inline-block;width:32px;height:32px;background:#474e50;border:1px solid #d1d5db;"></span>
  <span title="800 #2e3335" style="display:inline-block;width:32px;height:32px;background:#2e3335;border:1px solid #d1d5db;"></span>
  <span title="900 #000000" style="display:inline-block;width:32px;height:32px;background:#000000;border:1px solid #d1d5db;"></span>
</div>

## Live Semantic Mapping

- Scope: `neutral` -> `inherited_base`
  Exact black and white remain inherited from the shared neutral baseline.
- Scope: `brand` -> `boston_mills/neutral`
  The live semantic brand lane now resolves through the Boston Mills neutral family, with `boston_mills/neutral/700_source` as the default expressive source and `neutral/800` on the stronger surfaces.
- Scope: `brand_secondary` -> `boston_mills/neutral`
  The live secondary expressive lane follows the same neutral family.
- Scope: `border/brand` -> `boston_mills/neutral/400`
  The brand border lane is no longer treated as shared black.
- Scope: `on_surface/brand/*` -> `universal/white`
  Contrast text remains shared and is not hue-tinted.
- `variables/assets/logo` -> `Boston Mills / Brandywine`

## Review Readiness

- Subject: `Boston Mills / Brandywine neutral ramp shift`
  Rule: Keep `Snowgun Grey` anchored at `boston_mills/neutral/700_source`, preserve exact black at `boston_mills/neutral/900_source`, and use the neutral family for both expressive semantic lanes.
