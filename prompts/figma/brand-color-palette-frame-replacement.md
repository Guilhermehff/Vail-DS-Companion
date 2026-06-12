# Brand Color Palette Frame Replacement

## Purpose

Create or replace a brand-specific color documentation frame from a Universal color frame by remapping every documented color to variables in `_Global: Color` for a target brand.

## When to Use

Use this prompt when a Figma Foundations file already has a Universal color palette/documentation frame and you need a version for another brand. The workflow updates connected variables, visible token names, color values, RGB, HSL, hex, contrast checks, and the original palette reference.

This prompt is for Figma Console MCP. It can be destructive if the user chooses overwrite mode.

## Required Context

- Target Figma file URL
- Universal/source frame URL with node ID
- Target brand id, for example `okemo`
- Target brand display name, for example `Okemo`
- Output mode:
  - `duplicate` to preserve the Universal source and create a new brand frame
  - `overwrite` to replace the supplied frame in place
- Optional target placement section or page
- Optional source-to-brand family mapping when the brand has more than one plausible replacement family

## Expected Output

- Updated or newly duplicated Figma frame
- All color swatches bound to the correct `_Global: Color` variables
- Visible token names, hex, RGB, HSL, contrast values, and original palette values updated
- Screenshot verification
- Compact before/after report

## Prompt Text

```text
Use the repository `AGENTS.md` rules. Figma is the live source of truth. Use Figma Console MCP, not the official remote Figma MCP, for Figma reads/writes.

Task: create a brand-specific color palette documentation frame from a Universal source frame by replacing the displayed and connected colors with variables from `_Global: Color` for the target brand.

Target Figma file:
[TARGET_FILE_URL]

Universal source frame:
[UNIVERSAL_FRAME_URL_WITH_NODE_ID]

Target brand:
- brand_id: [BRAND_ID]
- display_name: [BRAND_DISPLAY_NAME]

Output mode:
[duplicate | overwrite]

Optional target placement:
[TARGET_SECTION_OR_PAGE_URL_WITH_NODE_ID]

Optional source-to-brand mapping:
Use this only if the brand has multiple candidate families and the mapping is already approved or explicitly supplied.
- universal/cool_neutral -> [brand/family]
- universal/warm_neutral -> [brand/family]
- universal/cyan -> [brand/family]
- universal/green -> [brand/family]
- brand primary -> [brand/family]
- brand secondary -> [brand/family]

Goal:
1. Inspect the Universal source frame and identify every documented color item.
2. Preserve the original Universal palette data in the resulting frame.
3. Replace the working/displayed palette with target brand variables from `_Global: Color`.
4. Update every connected color variable binding, visible token name, hex value, RGB value, HSL value, and contrast check.
5. Keep the existing documentation structure, component instances, grid behavior, auto layout, text styles, spacing, and visual hierarchy.
6. Do not invent variable values or mappings.

Required preflight:
1. Use `figma_get_status` with probe enabled.
2. Use `figma_list_open_files`.
3. Confirm the active file is the intended target file.
4. If multiple files are open or the active file is unclear, stop and ask.
5. Confirm whether output mode is `duplicate` or `overwrite`.
6. If output mode is `overwrite`, treat it as destructive and ask for explicit confirmation before writing.
7. Use `figma_execute` and native async Figma APIs:
   - `await figma.getNodeByIdAsync(nodeId)`
   - `await figma.variables.getLocalVariableCollectionsAsync()`
   - `await figma.variables.getLocalVariablesAsync()`
8. Do not use sync APIs such as `figma.getNodeById()`.

Variable inventory:
1. Find the local collection named `_Global: Color`.
2. Read all variables whose names start with `[BRAND_ID]/`.
3. Confirm each target family uses the governed 100-900 ramp where applicable.
4. Preserve `_source` suffixes exactly when they exist, for example `[brand]/[family]/500_source`.
5. If `[BRAND_ID]/` has no variables in `_Global: Color`, stop and report that the brand has no live global color variables.
6. If more than one brand family could replace a Universal family and no mapping is supplied, stop and ask for the mapping before writing.

Source frame inspection:
1. Read the source frame tree and all child instances/frames/text nodes.
2. For each documented color item, identify:
   - source bound variable ID and variable name, if any
   - displayed token name
   - displayed hex
   - displayed RGB
   - displayed HSL
   - displayed contrast check values
   - swatch fill or stroke bindings
   - foreground/background pairing used for contrast
   - whether the item belongs to the original palette section or the active replacement palette section
3. Build a table of source palette rows before writing.
4. Do not proceed if any color item cannot be mapped to a token path or if the frame structure is ambiguous.

Mapping rules:
1. Prefer exact step replacement: source step `100` maps to target step `100`, `200` to `200`, and so on.
2. If the source token uses `_source`, map by the numeric step first, then preserve the target brand's live `_source` token when that step has one.
3. If the target family lacks an exact step, stop and ask. Do not approximate.
4. Universal black and white may remain `universal/black` and `universal/white` unless the user explicitly supplies a brand-specific replacement.
5. Original palette rows must keep their original source values and bindings unless the frame design clearly expects original palette rows to be unbound reference text.
6. Active brand palette rows must bind to the target brand variables.

Color value calculation:
1. Resolve each target variable value through the `_Global: Color` collection mode `values`.
2. Convert every target color to:
   - HEX, uppercase 6-digit format, for example `#0057B8`
   - RGB, integer format, for example `0, 87, 184`
   - HSL, rounded to whole-number hue and percentage saturation/lightness, for example `212, 100%, 36%`
3. Use the same formatting style already visible in the source frame if it differs from the examples.
4. If alpha is not 1, report it and stop unless the source frame already supports alpha display.

Contrast checks:
1. Recalculate contrast using WCAG relative luminance.
2. For paired foreground/background items, use the actual paired variables in the documentation row.
3. For standalone palette swatches, calculate contrast against both `universal/white` and `universal/black` unless the frame already has a different explicit contrast convention.
4. Display contrast ratios with two decimals, for example `4.52:1`.
5. Update visible pass/fail state according to the source frame's existing thresholds and labels.
6. If no threshold is visible in the frame, use:
   - AA normal text: 4.5:1
   - AA large text: 3:1
   - AAA normal text: 7:1
7. Report any color that fails the source frame's intended contrast target.

Write rules:
1. If output mode is `duplicate`, clone the Universal source frame and rename the clone to `[BRAND_DISPLAY_NAME] Color Palette` or the naming pattern used by nearby frames.
2. If output mode is `overwrite`, update the supplied source frame in place only after explicit confirmation.
3. Use instance properties for documented values when component instances expose text/token/hex/RGB/HSL/contrast properties.
4. Do not edit internal text layers directly if the instance exposes component properties.
5. If no component property exists, edit the visible text node only after verifying it belongs to the target documentation item and is not inside a component instance.
6. Update bound variables on fills, strokes, effects, or other color-bearing properties using native Figma variable binding APIs.
7. Do not detach component instances unless explicitly necessary. If detaching seems necessary, stop and ask.
8. Preserve all layout structure. Do not convert a confirmed `GRID` parent to auto layout or an auto-layout frame to manual positioning.
9. If the frame has a dedicated Original Palette area, update it to show the source Universal palette values captured before replacement.
10. If the frame has no Original Palette area, create one only if the existing frame pattern includes comparable palette reference sections nearby. Otherwise stop and ask before adding new structure.

Verification:
1. After writing, take a screenshot of the resulting frame with `figma_capture_screenshot`.
2. Visually verify:
   - the frame is complete and not overlapped
   - swatches changed to the target brand colors
   - original palette values are still visible where required
   - token names, hex, RGB, HSL, and contrast text fit inside their containers
   - no stale Universal token names remain in the active brand palette area
3. Directly verify through `figma_execute`:
   - every active brand swatch is bound to the intended `_Global: Color` variable
   - every visible token name matches the bound variable name
   - every visible HEX/RGB/HSL value matches the resolved variable value
   - every visible contrast value matches the recalculated ratio
   - the original palette section still matches the captured source palette
4. If any mismatch remains, fix it and rerun verification before reporting complete.

Final report:
Return a compact table with:
- Row/item label
- Original token
- New token
- New HEX
- New RGB
- New HSL
- Contrast result
- Binding verified

Also report:
- Source frame node ID
- Result frame node ID
- Output mode used
- Number of color items updated
- Number of original palette items preserved
- Any failed contrast checks
- Any unmapped or skipped items

Stop conditions:
- Target file is not confirmed.
- The target brand is not present in `figma/brands/registry.yml` unless the user explicitly says this is a live-Figma-only sync.
- `_Global: Color` is missing.
- Brand color variables are missing.
- The mapping from Universal source rows to brand families is ambiguous.
- Any color item cannot be safely mapped.
- Output mode is `overwrite` and explicit destructive confirmation has not been given.
- Updating the original palette requires adding new frame structure that is not already present in the source pattern.

Do not:
- Use the official remote Figma MCP for this governance write.
- Write to a channel file.
- Invent color values, token names, contrast values, or family mappings.
- Create local export snapshots unless explicitly requested.
- Create a decision log unless a new governance exception or non-obvious mapping choice is approved during the work.
```
