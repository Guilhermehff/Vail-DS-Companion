# Mad River Mountain Color Preview

Review state: repo proposal only. This color set is not written in Figma yet; live
 Mad River color state in `figma/brands/mad_river_mountain/brand.yml` still reflects
 the older `river_blue` and `mountain_green` write.

## Original Source Swatches

- Source color: `Mad Black`
  Provided value: `#231f20`

- Source color: `Mountain Green`
  Provided value: `#014e37`

- Source color: `Nav Grey`
  Provided value: `#464e51`

## Universal Reuse

- Source color: `White background and reverse logo usage`
  Proposed token: `universal/white`
  Notes: The supplied guideline still relies on exact white for reverse applications
  and page background.

## Proposed Families

### Family: mad_black

Source anchor: `700_source`

<div>
  <span title="100 #f8f7f7" style="display:inline-block;width:32px;height:32px;background:#f8f7f7;border:1px solid #d1d5db;"></span>
  <span title="200 #ece9ea" style="display:inline-block;width:32px;height:32px;background:#ece9ea;border:1px solid #d1d5db;"></span>
  <span title="300 #cfc9ca" style="display:inline-block;width:32px;height:32px;background:#cfc9ca;border:1px solid #d1d5db;"></span>
  <span title="400 #aea3a6" style="display:inline-block;width:32px;height:32px;background:#aea3a6;border:1px solid #d1d5db;"></span>
  <span title="500 #8c7d81" style="display:inline-block;width:32px;height:32px;background:#8c7d81;border:1px solid #d1d5db;"></span>
  <span title="600 #51484a" style="display:inline-block;width:32px;height:32px;background:#51484a;border:1px solid #d1d5db;"></span>
  <span title="700 #231f20" style="display:inline-block;width:32px;height:32px;background:#231f20;border:1px solid #d1d5db;"></span>
  <span title="800 #181616" style="display:inline-block;width:32px;height:32px;background:#181616;border:1px solid #d1d5db;"></span>
  <span title="900 #100e0f" style="display:inline-block;width:32px;height:32px;background:#100e0f;border:1px solid #d1d5db;"></span>
</div>

### Family: mountain_green

Source anchor: `700_source`

<div>
  <span title="100 #f0fef8" style="display:inline-block;width:32px;height:32px;background:#f0fef8;border:1px solid #d1d5db;"></span>
  <span title="200 #e4f5ee" style="display:inline-block;width:32px;height:32px;background:#e4f5ee;border:1px solid #d1d5db;"></span>
  <span title="300 #b7d4c8" style="display:inline-block;width:32px;height:32px;background:#b7d4c8;border:1px solid #d1d5db;"></span>
  <span title="400 #91baa8" style="display:inline-block;width:32px;height:32px;background:#91baa8;border:1px solid #d1d5db;"></span>
  <span title="500 #6da08a" style="display:inline-block;width:32px;height:32px;background:#6da08a;border:1px solid #d1d5db;"></span>
  <span title="600 #4d7a68" style="display:inline-block;width:32px;height:32px;background:#4d7a68;border:1px solid #d1d5db;"></span>
  <span title="700 #014e37" style="display:inline-block;width:32px;height:32px;background:#014e37;border:1px solid #d1d5db;"></span>
  <span title="800 #013b2a" style="display:inline-block;width:32px;height:32px;background:#013b2a;border:1px solid #d1d5db;"></span>
  <span title="900 #00271c" style="display:inline-block;width:32px;height:32px;background:#00271c;border:1px solid #d1d5db;"></span>
</div>

### Family: nav_grey

Source anchor: `700_source`

<div>
  <span title="100 #f4f5f6" style="display:inline-block;width:32px;height:32px;background:#f4f5f6;border:1px solid #d1d5db;"></span>
  <span title="200 #e4e6e7" style="display:inline-block;width:32px;height:32px;background:#e4e6e7;border:1px solid #d1d5db;"></span>
  <span title="300 #c3c9cb" style="display:inline-block;width:32px;height:32px;background:#c3c9cb;border:1px solid #d1d5db;"></span>
  <span title="400 #a2abaf" style="display:inline-block;width:32px;height:32px;background:#a2abaf;border:1px solid #d1d5db;"></span>
  <span title="500 #818e92" style="display:inline-block;width:32px;height:32px;background:#818e92;border:1px solid #d1d5db;"></span>
  <span title="600 #636f73" style="display:inline-block;width:32px;height:32px;background:#636f73;border:1px solid #d1d5db;"></span>
  <span title="700 #464e51" style="display:inline-block;width:32px;height:32px;background:#464e51;border:1px solid #d1d5db;"></span>
  <span title="800 #353c3e" style="display:inline-block;width:32px;height:32px;background:#353c3e;border:1px solid #d1d5db;"></span>
  <span title="900 #272c2d" style="display:inline-block;width:32px;height:32px;background:#272c2d;border:1px solid #d1d5db;"></span>
</div>

## Proposed Semantic Mapping

- Scope: `neutral` -> `inherited_base`
  This repo proposal keeps the shared neutral semantic lane untouched until the new
  source set is approved for a live Figma write.
- Scope: `brand` -> `mad_river_mountain/mad_black`
  Mad Black becomes the proposed primary expressive lane from the updated guideline.
- Scope: `brand_secondary` -> `mad_river_mountain/mountain_green`
  Mountain Green is the approved supporting expressive lane for this pass.
- Global-only candidate: `mad_river_mountain/nav_grey`
  Governed raw family kept outside the semantic mapping for now.
- `assets/brand` -> `Mad River Mountain`

## Review Readiness

- Subject: `Mad River Mountain primary expressive mapping`
  Rule: Promote `mad_black` to the `brand/*` semantic lane when the live write is approved.
- Subject: `Mad River Mountain supporting expressive mapping`
  Rule: Use `mountain_green` for `brand_secondary/*`; keep `nav_grey` global-only unless
  a later semantic neutral decision is approved.
