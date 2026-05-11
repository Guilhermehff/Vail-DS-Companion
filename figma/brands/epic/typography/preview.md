# Epic Typography Preview

Review state: live Figma primitives recorded from `Foundations - Epic` on 2026-04-27.

## Source Of Truth

- Figma file: `Foundations - Epic`
- File key: `4Y5qG5CswdHwA0sdSGHCas`
- Global typography collection: `_Global: Typography` (`VariableCollectionId:2047:143`)
- Mode: `values`
- Design system scope: `standalone`

## Original Source Roles

- Source role: `brand_headlines`
  Family: `Brandon Grotesque`
  Style: `Brandon Grotesque Black`
  Weight label: `Black`
  Usage scope: `brand_headlines`
  Case: `all_caps`
  Tracking: `50`
  Notes: Brand headlines should be all caps and at least two times the size of body copy.

- Source role: `secondary_headlines_and_headings`
  Family: `Montserrat`
  Weight label: `Bold`
  Usage scope: `secondary_headlines_headings`
  Case: `sentence_case_or_all_caps`
  Tracking: `0`

- Source role: `body_copy`
  Family: `Montserrat`
  Weight label: `Regular`
  Usage scope: `reading_copy`
  Case: `sentence_case`
  Tracking: `0`
  Notes: Standard digital body copy should not be smaller than 14 pt.

- Source role: `subheads`
  Family: `Montserrat`
  Weight label: `Bold or Semibold`
  Usage scope: `subheads`
  Tracking: `0`
  Notes: Numbers and pricing should match surrounding text styling.

- Source role: `legal_and_disclosures`
  Family: `Montserrat`
  Weight label: `Regular with optional Bold highlights`
  Usage scope: `legal_and_disclosures`
  Case: `sentence_case`
  Tracking: `0`
  Notes: Sizing should not be smaller than 11 pt.

## Live Figma Primitives

### Families

- `family/01`: `Brandon Grotesque`
- `family/02`: `Montserrat`
- `family_safe/01`: `Arial`

### Sizes

- `size/100`: `14`
- `size/200`: `16`
- `size/300`: `18`
- `size/400`: `20`
- `size/500`: `24`
- `size/600`: `30`
- `size/700`: `36`
- `size/800`: `40`

### Weights

- `weight/black`: `900`
- `weight/bold`: `700`
- `weight/semibold`: `600`
- `weight/medium`: `500`
- `weight/normal`: `400`

## Role Recipes

### Role: brand_headlines

Proposed family token: `family/01`

Proposed weight token: `weight/black`

Recipe notes:

- Case: `all_caps`
- Tracking: `50`
- Notes: Signature Epic headline treatment. Source says size should be at least two times body copy.

### Role: secondary_headlines_and_headings

Proposed family token: `family/02`

Proposed weight token: `weight/bold`

Recipe notes:

- Case: `sentence_case_or_all_caps`
- Tracking: `0`

### Role: body_copy

Proposed family token: `family/02`

Proposed weight token: `weight/normal`

Proposed minimum size token: `size/100`

Recipe notes:

- Case: `sentence_case`
- Tracking: `0`
- Notes: Source says standard digital body copy should not be smaller than 14 pt.

### Role: subheads

Proposed family token: `family/02`

Proposed weight tokens: `weight/bold` or `weight/semibold`

Recipe notes:

- Tracking: `0`
- Notes: Source says numbers and pricing should match the surrounding text styling.

### Role: legal_and_disclosures

Proposed family token: `family/02`

Proposed weight token: `weight/normal`, with optional `weight/bold` highlights

Recipe notes:

- Case: `sentence_case`
- Tracking: `0`
- Notes: Source minimum is 11 pt; live Figma global size ladder starts at `size/100` = 14.

## Review Notes

- Epic typography is scoped to the standalone Epic Foundations file.
- The live safe-family primitive is `Arial`.
- The live size ladder starts at 14, so the source legal minimum of 11 pt is guidance, not currently represented as a global typography size primitive.
