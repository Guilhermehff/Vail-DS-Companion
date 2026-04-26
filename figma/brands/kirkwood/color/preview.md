# Kirkwood Color Preview

Review state: written in figma. Verify live write state in `figma/brands/kirkwood/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Black C`
  Provided value: `#000000`
  Usage scope: `foundational palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `0 0 0 100` and HEX `#000000`.

- Source color: `Cool Grey 9`
  Provided value: `#6d6e70`
  Usage scope: `foundational palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `0 0 0 70` and HEX `#6D6E70`.

- Source color: `Cool Grey 1`
  Provided value: `#f1f1f2`
  Usage scope: `foundational palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `0 0 0 5` and HEX `#F1F1F2`.

- Source color: `White`
  Provided value: `#ffffff`
  Usage scope: `foundational palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `0 0 0 0` and HEX `#FFFFFF`.

- Source color: `Orange 021 C`
  Provided value: `#f15a2b`
  Usage scope: `accent palette`
  Channel restrictions: `used as highlight in source note`
  Notes: Source image lists CMYK `0 80 93 0` and HEX `#F15A2B`.

- Source color: `648 C`
  Provided value: `#004c69`
  Usage scope: `accent palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `87 42 20 47` and HEX `#004C69`.

- Source color: `633 C`
  Provided value: `#0f758b`
  Usage scope: `accent palette`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `87 42 36 7` and HEX `#0F758B`.

- Source color: `642 C`
  Provided value: `#d0e2e9`
  Usage scope: `accent palette approved for neutral-support use`
  Channel restrictions: `not specified in source`
  Notes: Source image lists CMYK `17 8 7 1` and HEX `#D0E2E9`.

## Universal Reuse

- Source color: `White`
  Proposed token: `universal/white`
  Notes: Exact match to the existing universal white primitive.

- Source color: `Black C`
  Proposed token: `universal/black`
  Notes: Exact match to the existing universal black primitive.

## Color Proportion Guidance

Source basis: The supplied Kirkwood visual-guidelines page states that black, white, and gray should dominate the design when blue tones are already present through outdoor photography, and that orange should be used as the highlight. The adjacent pie chart describes content distribution rather than a direct color percentage table.

### Outdoor Photography Compositions

- Intent: `Foundational neutrals dominate. Orange 021 C stays as the main highlight color. The blue accents should usually arrive through photography or smaller supporting moments rather than as the leading solid field.`
- Dominant palette:
  `White` -> `universal/white`
  `Cool Grey 1` -> `kirkwood/cool_gray/200_source`
  `Cool Grey 9` -> `kirkwood/cool_gray/700_source`
  `Black C` -> `universal/black`
- Supporting palette:
  `Orange 021 C` -> `kirkwood/orange/500_source`
  `642 C` -> `kirkwood/blue/300_source`
  `633 C` -> `kirkwood/blue/600_source`
  `648 C` -> `kirkwood/blue/700_source`
- Notes:
  The source explicitly says orange is used as the highlight.
  The source explicitly says the palette blues often occur naturally in outdoor photography.

## Proposed Families

### Family: orange

Source anchor: `500_source`

<div>
  <span title="100 #fff4ef" style="display:inline-block;width:32px;height:32px;background:#fff4ef;border:1px solid #d1d5db;"></span>
  <span title="200 #ffe4d7" style="display:inline-block;width:32px;height:32px;background:#ffe4d7;border:1px solid #d1d5db;"></span>
  <span title="300 #ffae92" style="display:inline-block;width:32px;height:32px;background:#ffae92;border:1px solid #d1d5db;"></span>
  <span title="400 #ff8561" style="display:inline-block;width:32px;height:32px;background:#ff8561;border:1px solid #d1d5db;"></span>
  <span title="500 #f15a2b" style="display:inline-block;width:32px;height:32px;background:#f15a2b;border:1px solid #d1d5db;"></span>
  <span title="600 #c34c28" style="display:inline-block;width:32px;height:32px;background:#c34c28;border:1px solid #d1d5db;"></span>
  <span title="700 #9c381a" style="display:inline-block;width:32px;height:32px;background:#9c381a;border:1px solid #d1d5db;"></span>
  <span title="800 #742a13" style="display:inline-block;width:32px;height:32px;background:#742a13;border:1px solid #d1d5db;"></span>
  <span title="900 #2e1109" style="display:inline-block;width:32px;height:32px;background:#2e1109;border:1px solid #d1d5db;"></span>
</div>

### Family: blue

Source anchors: `300_source / 600_source / 700_source`

<div>
  <span title="100 #eef9fd" style="display:inline-block;width:32px;height:32px;background:#eef9fd;border:1px solid #d1d5db;"></span>
  <span title="200 #d9eef5" style="display:inline-block;width:32px;height:32px;background:#d9eef5;border:1px solid #d1d5db;"></span>
  <span title="300 #d0e2e9" style="display:inline-block;width:32px;height:32px;background:#d0e2e9;border:1px solid #d1d5db;"></span>
  <span title="400 #9fcdda" style="display:inline-block;width:32px;height:32px;background:#9fcdda;border:1px solid #d1d5db;"></span>
  <span title="500 #5fb0c2" style="display:inline-block;width:32px;height:32px;background:#5fb0c2;border:1px solid #d1d5db;"></span>
  <span title="600 #0f758b" style="display:inline-block;width:32px;height:32px;background:#0f758b;border:1px solid #d1d5db;"></span>
  <span title="700 #004c69" style="display:inline-block;width:32px;height:32px;background:#004c69;border:1px solid #d1d5db;"></span>
  <span title="800 #00364b" style="display:inline-block;width:32px;height:32px;background:#00364b;border:1px solid #d1d5db;"></span>
  <span title="900 #00202e" style="display:inline-block;width:32px;height:32px;background:#00202e;border:1px solid #d1d5db;"></span>
</div>


### Family: cool_gray

Source anchors: `200_source / 700_source`

<div>
  <span title="100 #f7f7f7" style="display:inline-block;width:32px;height:32px;background:#f7f7f7;border:1px solid #d1d5db;"></span>
  <span title="200 #f1f1f2" style="display:inline-block;width:32px;height:32px;background:#f1f1f2;border:1px solid #d1d5db;"></span>
  <span title="300 #d9dcde" style="display:inline-block;width:32px;height:32px;background:#d9dcde;border:1px solid #d1d5db;"></span>
  <span title="400 #bec4c7" style="display:inline-block;width:32px;height:32px;background:#bec4c7;border:1px solid #d1d5db;"></span>
  <span title="500 #a3abaf" style="display:inline-block;width:32px;height:32px;background:#a3abaf;border:1px solid #d1d5db;"></span>
  <span title="600 #889296" style="display:inline-block;width:32px;height:32px;background:#889296;border:1px solid #d1d5db;"></span>
  <span title="700 #6d6e70" style="display:inline-block;width:32px;height:32px;background:#6d6e70;border:1px solid #d1d5db;"></span>
  <span title="800 #4b4b4d" style="display:inline-block;width:32px;height:32px;background:#4b4b4d;border:1px solid #d1d5db;"></span>
  <span title="900 #2e2e2f" style="display:inline-block;width:32px;height:32px;background:#2e2e2f;border:1px solid #d1d5db;"></span>
</div>


## Review Notes

- Orange 021 C lands at `500` because the supplied swatch behaves as a vivid mid-tone highlight rather than a dark foundation color.
- `blue` is a composite live family that preserves `642 C` at `300`, `633 C` at `600`, and `648 C` at `700`.
- `cool_gray` follows the live Figma ramp, with `Cool Grey 1` at `200` and `Cool Grey 9` at `700`.

## Review Readiness

- Subject: `Kirkwood branded neutral ladder`
  Channels: `web, email, ads`
  Rule: Treat `Cool Grey 1` and `Cool Grey 9` as the source anchors inside `kirkwood/cool_gray/*`.
  Source basis: User approval in chat plus the foundational palette image.

- Subject: `Kirkwood accent slot mapping`
  Channels: `web, email, ads`
  Rule: Use Orange 021 C as `brand/*` and the consolidated blue family as the supporting accent family.
  Source basis: The supplied palette image and approved semantic mapping choice.
