# Whitetail Resort Color Preview

Review state: written in figma. Verify live write state in `figma/brands/whitetail_resort/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Two Top Green`
  Provided value: `#233d34`

- Source color: `Black`
  Provided value: `#000000`

- Source color: `White`
  Provided value: `#ffffff`

## Universal Reuse

- Source color: `Black`
  Proposed token: `universal/black`
  Notes: Exact match.

- Source color: `White`
  Proposed token: `universal/white`
  Notes: Exact match.

## Proposed Families

### Family: two_top_green

Source anchor: `700_source`

<div>
  <span title="100 #f3f9f7" style="display:inline-block;width:32px;height:32px;background:#f3f9f7;border:1px solid #d1d5db;"></span>
  <span title="200 #e3f1ec" style="display:inline-block;width:32px;height:32px;background:#e3f1ec;border:1px solid #d1d5db;"></span>
  <span title="300 #c7e3da" style="display:inline-block;width:32px;height:32px;background:#c7e3da;border:1px solid #d1d5db;"></span>
  <span title="400 #9fd0c2" style="display:inline-block;width:32px;height:32px;background:#9fd0c2;border:1px solid #d1d5db;"></span>
  <span title="500 #74b7a5" style="display:inline-block;width:32px;height:32px;background:#74b7a5;border:1px solid #d1d5db;"></span>
  <span title="600 #4f9a87" style="display:inline-block;width:32px;height:32px;background:#4f9a87;border:1px solid #d1d5db;"></span>
  <span title="700 #233d34" style="display:inline-block;width:32px;height:32px;background:#233d34;border:1px solid #d1d5db;"></span>
  <span title="800 #1b2f28" style="display:inline-block;width:32px;height:32px;background:#1b2f28;border:1px solid #d1d5db;"></span>
  <span title="900 #0f1f1a" style="display:inline-block;width:32px;height:32px;background:#0f1f1a;border:1px solid #d1d5db;"></span>
</div>


### Family: neutral

Source anchor: `500_source`

<div>
  <span title="100 #ffffff" style="display:inline-block;width:32px;height:32px;background:#ffffff;border:1px solid #d1d5db;"></span>
  <span title="200 #f4f4f5" style="display:inline-block;width:32px;height:32px;background:#f4f4f5;border:1px solid #d1d5db;"></span>
  <span title="300 #cfcfd2" style="display:inline-block;width:32px;height:32px;background:#cfcfd2;border:1px solid #d1d5db;"></span>
  <span title="400 #a9aaaf" style="display:inline-block;width:32px;height:32px;background:#a9aaaf;border:1px solid #d1d5db;"></span>
  <span title="500 #7c7d83" style="display:inline-block;width:32px;height:32px;background:#7c7d83;border:1px solid #d1d5db;"></span>
  <span title="600 #55565c" style="display:inline-block;width:32px;height:32px;background:#55565c;border:1px solid #d1d5db;"></span>
  <span title="700 #333333" style="display:inline-block;width:32px;height:32px;background:#333333;border:1px solid #d1d5db;"></span>
  <span title="800 #2b2a2b" style="display:inline-block;width:32px;height:32px;background:#2b2a2b;border:1px solid #d1d5db;"></span>
  <span title="900 #231f20" style="display:inline-block;width:32px;height:32px;background:#231f20;border:1px solid #d1d5db;"></span>
</div>


## Live Semantic Mapping

- Scope: `neutral` -> `inherited_base`
  Exact black and white remain inherited.
- Scope: `brand` -> `whitetail_resort/two_top_green`
  One non-neutral brand hue drives the first expressive lane.
- Scope: `brand_secondary` -> `whitetail_resort/two_top_green`
  One non-neutral brand hue drives the second expressive lane as well.
- Global-only families: `whitetail_resort/neutral`
- `assets/brand` -> `Whitetail Resort`

## Review Readiness

- Subject: `Whitetail Resort single-family expressive mapping`
  Rule: Use `two_top_green` for both expressive semantic lanes.
