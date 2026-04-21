# Whistler Blackcomb Color Preview

Review state: written in figma. Verify live write state in `figma/brands/whistler_blackcomb/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Red`
  Provided value: `#cc0000`
  Usage scope: `primary brand palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists HEX CC0000, RGB 204 0 0, and CMYK 13 100 100 4.

- Source color: `Black`
  Provided value: `#000000`
  Usage scope: `primary brand palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists RGB 0 0 0 and CMYK 0 0 0 100.

- Source color: `White`
  Provided value: `#ffffff`
  Usage scope: `primary brand palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists RGB 255 255 255 and CMYK 0 0 0 0.

## Universal Reuse

- Source color: `Black`
  Proposed token: `universal/black`
  Notes: Exact match to the shared universal black primitive.

- Source color: `White`
  Proposed token: `universal/white`
  Notes: Exact match to the shared universal white primitive.

## Color Proportion Guidance

Source basis: The official Whistler Blackcomb guide explicitly calls for an even ratio of red, black, and white. The source does not break that rule into exact integer percentages beyond equal thirds.

### Brand Touchpoints

- Intent: `Red, black, and white should be held in balance so no single one of the three becomes the only field color in a design.`
- Proportions:
  `Red` -> `whistler_blackcomb/red/600` (`33%`) The source calls for an even share across the three brand colors.
  `Black` -> `universal/black` (`33%`) The source calls for an even share across the three brand colors.
  `White` -> `universal/white` (`33%`) The source calls for an even share across the three brand colors.
- Notes:
  Treat these as equal thirds rather than as audited integer totals.
  The source also states that no design should resolve to all red, all black, or all white.

## Proposed Families

### Family: neutral

Source anchors: `100_source / 900_source`

<div>
  <span title="100 #ffffff" style="display:inline-block;width:32px;height:32px;background:#ffffff;border:1px solid #d1d5db;"></span>
  <span title="200 #e6e6e6" style="display:inline-block;width:32px;height:32px;background:#e6e6e6;border:1px solid #d1d5db;"></span>
  <span title="300 #cccccc" style="display:inline-block;width:32px;height:32px;background:#cccccc;border:1px solid #d1d5db;"></span>
  <span title="400 #a6a6a6" style="display:inline-block;width:32px;height:32px;background:#a6a6a6;border:1px solid #d1d5db;"></span>
  <span title="500 #808080" style="display:inline-block;width:32px;height:32px;background:#808080;border:1px solid #d1d5db;"></span>
  <span title="600 #595959" style="display:inline-block;width:32px;height:32px;background:#595959;border:1px solid #d1d5db;"></span>
  <span title="700 #404040" style="display:inline-block;width:32px;height:32px;background:#404040;border:1px solid #d1d5db;"></span>
  <span title="800 #262626" style="display:inline-block;width:32px;height:32px;background:#262626;border:1px solid #d1d5db;"></span>
  <span title="900 #000000" style="display:inline-block;width:32px;height:32px;background:#000000;border:1px solid #d1d5db;"></span>
</div>

### Family: red

Source anchor: `600_source`

<div>
  <span title="100 #fff1ef" style="display:inline-block;width:32px;height:32px;background:#fff1ef;border:1px solid #d1d5db;"></span>
  <span title="200 #ffded8" style="display:inline-block;width:32px;height:32px;background:#ffded8;border:1px solid #d1d5db;"></span>
  <span title="300 #ff8f7e" style="display:inline-block;width:32px;height:32px;background:#ff8f7e;border:1px solid #d1d5db;"></span>
  <span title="400 #ff604e" style="display:inline-block;width:32px;height:32px;background:#ff604e;border:1px solid #d1d5db;"></span>
  <span title="500 #ff0000" style="display:inline-block;width:32px;height:32px;background:#ff0000;border:1px solid #d1d5db;"></span>
  <span title="600 #cc0000" style="display:inline-block;width:32px;height:32px;background:#cc0000;border:1px solid #d1d5db;"></span>
  <span title="700 #9c0000" style="display:inline-block;width:32px;height:32px;background:#9c0000;border:1px solid #d1d5db;"></span>
  <span title="800 #6e0000" style="display:inline-block;width:32px;height:32px;background:#6e0000;border:1px solid #d1d5db;"></span>
  <span title="900 #300000" style="display:inline-block;width:32px;height:32px;background:#300000;border:1px solid #d1d5db;"></span>
</div>

## Review Notes

- Whistler Blackcomb Red lands at `600` because the supplied swatch is darker than pure digital red but still sits above the deepest accent range.
- Exact black and white should remain shared through `universal/black` and `universal/white`.
- Live Figma now also carries `whistler_blackcomb/neutral/*` while the original exact black and white source matches still remain documented against the shared universal primitives.

## Live Semantic Mapping

- `color/surface/neutral/*`, `color/on_surface/neutral/*`, `color/foreground/default`, `color/foreground/subtle`, `color/border/default`, `color/border/subtle` -> `inherited_base`
  The supplied black and white are exact universal matches, so the shared neutral role set remains inherited from the semantic base collection.
- `color/surface/brand/*`, `color/on_surface/brand/*`, `color/foreground/brand`, `color/border/brand` -> `whistler_blackcomb/red`
  Red is the primary Whistler Blackcomb expressive lane.
- `color/surface/brand_secondary/*`, `color/on_surface/brand_secondary/*`, `color/foreground/brand_secondary`, `color/border/brand_secondary` -> `whistler_blackcomb/neutral`
  The live secondary expressive lane now resolves through the Whistler Blackcomb neutral family.
- `variables/assets/logo` -> `Whistler Blackcomb`
  The live `Semantic: Theme` schema includes `variables/assets/logo`, and each brand extension overrides it to the brand display name string.

## Review Readiness

- Subject: `Whistler Blackcomb neutral reuse`
  Channels: `web, email, ads`
  Rule: Keep exact black and white on the shared universal primitives rather than creating duplicate brand exact tokens.
  Source basis: The supplied palette exactly matches the governed universal values.

- Subject: `Whistler Blackcomb expressive lane coverage`
  Channels: `web, email, ads`
  Rule: Use the red family for both `brand/*` and `brand_secondary/*` in the first semantic pass because the official palette supplies only one expressive hue.
  Source basis: The supplied palette defines red, black, and white only, and the accepted semantic family model permits same-family mapping when no second expressive hue is defined.
