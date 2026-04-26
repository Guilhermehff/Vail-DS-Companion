# Wildcat Mountain Color Preview

Review state: written in figma. Verify live write state in `figma/brands/wildcat_mountain/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Wildcat Green`
  Provided value: `#007067`

- Source color: `Wildcat Tan`
  Provided value: `#e8e1be`

- Source color: `Wildcat Teal`
  Provided value: `#008a7e`

- Source color: `Wedding Blue`
  Provided value: `#53c0c4`
  Notes: Preserved as source provenance only. Not a live raw family in Figma.

## Universal Reuse

- Source color: `Black logo variation`
  Proposed token: `universal/black`
  Notes: Exact black remains shared through the universal neutral baseline.

- Source color: `White logo variation`
  Proposed token: `universal/white`
  Notes: Exact white remains shared through the universal neutral baseline.

## Proposed Families

### Family: wildcat_green

Source anchor: `600_source`

<div>
  <span title="100 #eaf6f4" style="display:inline-block;width:32px;height:32px;background:#eaf6f4;border:1px solid #d1d5db;"></span>
  <span title="200 #d3ece8" style="display:inline-block;width:32px;height:32px;background:#d3ece8;border:1px solid #d1d5db;"></span>
  <span title="300 #a9d9d2" style="display:inline-block;width:32px;height:32px;background:#a9d9d2;border:1px solid #d1d5db;"></span>
  <span title="400 #7fc2b8" style="display:inline-block;width:32px;height:32px;background:#7fc2b8;border:1px solid #d1d5db;"></span>
  <span title="500 #4fa79c" style="display:inline-block;width:32px;height:32px;background:#4fa79c;border:1px solid #d1d5db;"></span>
  <span title="600 #007067" style="display:inline-block;width:32px;height:32px;background:#007067;border:1px solid #d1d5db;"></span>
  <span title="700 #005a54" style="display:inline-block;width:32px;height:32px;background:#005a54;border:1px solid #d1d5db;"></span>
  <span title="800 #00443f" style="display:inline-block;width:32px;height:32px;background:#00443f;border:1px solid #d1d5db;"></span>
  <span title="900 #002e2b" style="display:inline-block;width:32px;height:32px;background:#002e2b;border:1px solid #d1d5db;"></span>
</div>


### Family: wildcat_tan

Source anchor: `400_source`

<div>
  <span title="100 #fbf8ee" style="display:inline-block;width:32px;height:32px;background:#fbf8ee;border:1px solid #d1d5db;"></span>
  <span title="200 #f3ecd9" style="display:inline-block;width:32px;height:32px;background:#f3ecd9;border:1px solid #d1d5db;"></span>
  <span title="300 #e6d8b5" style="display:inline-block;width:32px;height:32px;background:#e6d8b5;border:1px solid #d1d5db;"></span>
  <span title="400 #e8e1be" style="display:inline-block;width:32px;height:32px;background:#e8e1be;border:1px solid #d1d5db;"></span>
  <span title="500 #c9b892" style="display:inline-block;width:32px;height:32px;background:#c9b892;border:1px solid #d1d5db;"></span>
  <span title="600 #a79573" style="display:inline-block;width:32px;height:32px;background:#a79573;border:1px solid #d1d5db;"></span>
  <span title="700 #85755a" style="display:inline-block;width:32px;height:32px;background:#85755a;border:1px solid #d1d5db;"></span>
  <span title="800 #5e5240" style="display:inline-block;width:32px;height:32px;background:#5e5240;border:1px solid #d1d5db;"></span>
  <span title="900 #3f372b" style="display:inline-block;width:32px;height:32px;background:#3f372b;border:1px solid #d1d5db;"></span>
</div>


### Family: wildcat_teal

Source anchor: `700_source`

<div>
  <span title="100 #d0e9e7" style="display:inline-block;width:32px;height:32px;background:#d0e9e7;border:1px solid #d1d5db;"></span>
  <span title="200 #b5ddda" style="display:inline-block;width:32px;height:32px;background:#b5ddda;border:1px solid #d1d5db;"></span>
  <span title="300 #7ec4be" style="display:inline-block;width:32px;height:32px;background:#7ec4be;border:1px solid #d1d5db;"></span>
  <span title="400 #61b7af" style="display:inline-block;width:32px;height:32px;background:#61b7af;border:1px solid #d1d5db;"></span>
  <span title="500 #43a9a0" style="display:inline-block;width:32px;height:32px;background:#43a9a0;border:1px solid #d1d5db;"></span>
  <span title="600 #249b90" style="display:inline-block;width:32px;height:32px;background:#249b90;border:1px solid #d1d5db;"></span>
  <span title="700 #008a7e" style="display:inline-block;width:32px;height:32px;background:#008a7e;border:1px solid #d1d5db;"></span>
  <span title="800 #005b53" style="display:inline-block;width:32px;height:32px;background:#005b53;border:1px solid #d1d5db;"></span>
  <span title="900 #00322e" style="display:inline-block;width:32px;height:32px;background:#00322e;border:1px solid #d1d5db;"></span>
</div>

## Live Semantic Mapping

- Scope: `neutral` -> `inherited_base`
  Exact black and white remain inherited from the shared neutral baseline.
- Scope: `brand` -> `wildcat_mountain/wildcat_green`
  Wildcat Green is the primary all-season brand color and drives the first expressive lane.
- Scope: `brand_secondary` -> `wildcat_mountain/wildcat_teal`
  Wildcat Teal is the most reusable supporting accent for the second expressive lane.
- Global-only family: `wildcat_mountain/wildcat_tan`
- `variables/assets/logo` -> `Wildcat Mountain`

## Review Readiness

- Subject: `Wildcat Mountain expressive mapping`
  Rule: Use `wildcat_green` for `brand/*` and `wildcat_teal` for `brand_secondary/*`.

- Subject: `Wildcat Mountain extra families`
  Rule: Keep `wildcat_tan` as a governed raw-only family in the first pass; preserve Wedding Blue as source provenance only.
