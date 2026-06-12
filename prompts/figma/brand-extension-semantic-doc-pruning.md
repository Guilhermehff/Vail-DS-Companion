# Brand Extension Semantic Doc Pruning

## Purpose

Update semantic documentation sections for multiple brand extensions so each brand documents only the semantic variables effectively overridden by that brand's Semantic extension collection.

## When to Use

Use this prompt when pruning or correcting brand-specific semantic documentation in a Figma Foundations file. This prompt is for destructive Figma documentation cleanup and requires Figma Console MCP.

## Required Context

- Target Figma file URL
- Brand names
- Brand Semantic extension collection names
- Brand documentation section URLs with node IDs
- Universal semantic documentation source node
- Completed example section nodes

## Expected Output

- Updated Figma brand documentation sections
- Per-brand verification report
- Final compact summary table

## Prompt Text

```text
Use the repository `AGENTS.md` rules. Figma is the live source of truth. Use Figma Console MCP, not the official remote Figma MCP, for Figma reads/writes.

Task: create semantic documentation for multiple brand extensions by pruning each brand's documentation section to only the variables overridden by that brand's Semantic extension collection.

Target Figma file:
[TARGET_FILE]

Brands to update, in order:
1. Brand name: `[BRAND_1_NAME]`
   Brand extension collection name: `[BRAND_1_EXTENSION_COLLECTION_NAME]`
   Brand documentation section:
   `[PASTE BRAND 1 SECTION URL WITH NODE ID]`

2. Brand name: `[BRAND_2_NAME]`
   Brand extension collection name: `[BRAND_2_EXTENSION_COLLECTION_NAME]`
   Brand documentation section:
   `[PASTE BRAND 2 SECTION URL WITH NODE ID]`

3. Brand name: `[BRAND_3_NAME]`
   Brand extension collection name: `[BRAND_3_EXTENSION_COLLECTION_NAME]`
   Brand documentation section:
   `[PASTE BRAND 3 SECTION URL WITH NODE ID]`

Reference nodes:
- Universal semantic documentation source:
[TARGET_LINK]
- Completed example 1, Afton Alps:
[TARGET_LINK]

Goal:
For each listed brand, update the semantic documentation section so it matches the completed examples:
1. Keep only semantic variables that are actually overridden by that brand's Semantic extension collection.
2. Delete documentation rows/cards/items for variables that are not overridden by that brand.
3. For each kept documented variable, update:
   - the visible alias/token display value
   - the documentation component's overridden state/mode
4. Preserve the existing documentation structure, spacing, typography, component instances, and automatic grid behavior.
5. Process brands sequentially, one brand at a time. Do not run brand writes in parallel.

Required preflight:
1. Use `figma_get_status` with probe enabled.
2. Use `figma_list_open_files`.
3. Confirm the active file is the intended target file.
4. Confirm only this file is the write target. If multiple files are open or the active file is unclear, stop and ask.
5. Inspect the target brand sections, completed examples, and the Universal source before writing.
6. Use `figma_execute` and native async Figma APIs:
   - `await figma.getNodeByIdAsync(nodeId)`
   - `await node.getMainComponentAsync()`
   - `await figma.variables.getLocalVariableCollectionsAsync()`
   - `await figma.variables.getLocalVariablesAsync()`
7. Do not use sync APIs such as `figma.getNodeById()`.

Batch write constraint:
You may proceed with destructive writes for each listed brand only if all of the following are true:
1. The target file is still the same confirmed file.
2. The target brand section exists.
3. The brand extension collection exists.
4. All documented items map cleanly to known semantic variable paths.
5. There are no unmatched token paths or ambiguous mappings.
6. The computed keep/delete counts are reported before writing each brand.
7. The previous brand, if any, completed verification successfully.

Stop and ask if any brand has ambiguity, missing nodes, missing collections, unmatched token paths, unexpected structure, alias mismatch after correction, or failed verification.

Variable logic:
1. Find the parent collection `Semantic: Theme`.
2. For each brand, find the brand extension collection by its listed collection name.
3. Read `extensionCollection.variableOverrides`.
4. Treat only base semantic variables present in `variableOverrides` as candidate documented variables.
5. Verify each override with:
   `await baseVariable.valuesByModeForCollectionAsync(extensionCollection)`
6. Include recorded overrides even when they resolve to the same alias target or literal value as the base mode, because some brand documentation needs explicit override state.
7. Do not invent variable mappings.

Alias/name update rules:
1. For every kept overridden documentation item, update both:
   - the override state/property
   - the visible alias token property/text
2. If the resolved extension value is a variable alias, display the target variable name, for example:
   - `beaver_creek/silver/500_source`
   - `alpine_valley/alpine/300_source`
   - `attitash/family/01`
3. If the resolved extension value is a string, boolean, or number, display that literal value.
4. For Combo swatches:
   - update `Surface alias#...` only when the exposed property key starts with exactly `Surface alias`
   - update `On-surface alias#...` only when the exposed property key starts with exactly `On-surface alias`
   - update `Surface token#...` only from the exact `Surface token` property
   - update `On-surface token#...` only from the exact `On-surface token` property
   - set `Override` to `Surface`, `On-surface`, or `Both`
5. Do not use broad substring matching for combo properties.
   - `surface alias` can accidentally match `On-surface alias`.
   - Use exact regex-style matching such as:
     - `/^Surface alias(?:#|$)/i`
     - `/^On[-_ ]surface alias(?:#|$)/i`
     - `/^Surface token(?:#|$)/i`
     - `/^On[-_ ]surface token(?:#|$)/i`
6. For Foreground, Border, Typography, and Token cards:
   - update the exposed `Alias token#...` property to the resolved extension target
   - set `Override = TRUE`

Component state rules:
1. Combo swatch:
   - If only the surface token is overridden, set `Override = Surface`.
   - If only the on-surface token is overridden, set `Override = On-surface`.
   - If both surface and on-surface tokens are overridden, set `Override = Both`.
2. Foreground, border, typography, and token card:
   - Since non-overridden variables should be removed, all remaining items with an `Override` property should show `Override = TRUE`.
3. Important sequencing:
   - Set the component override state/variant first.
   - Then set the exposed alias text properties afterward.
   - Variant changes can reset exposed text properties, so alias text must be written after the final variant state is applied.
4. Use instance properties, preferably via native `node.setProperties()` in `figma_execute` or `figma_set_instance_properties`.
5. Do not edit internal text layers directly if the instance exposes component properties.
6. Do not detach instances unless explicitly necessary. If detaching seems necessary, stop and ask.

Grid handling:
1. All documentation `GRID` parents in this file use automatic placement.
2. Do not call `setGridChildPosition()`.
3. Do not convert `GRID` parents to auto layout.
4. Preserve the existing child layer order.
5. Delete non-overridden children from their current `GRID` parents and let Figma's automatic grid placement reflow the remaining items.
6. After deletion, inspect each affected `GRID` parent to confirm:
   - only overridden documentation items remain
   - child count matches the expected kept items
   - no blank/orphan grid children remain

Cleanup rules:
1. After deleting non-overridden doc items, remove empty documentation containers such as:
   - empty `Color doc`
   - empty `Typography doc`
   - empty `Variable doc`
   - empty `Token group`
   - empty `Semantic Grid`
2. Do not traverse into component instance internals for deletion.
3. Only delete top-level documentation instances and normal wrapper frames in the target brand section.
4. Remove orphan headings whose section no longer contains any documented token items.
5. Resize the target brand section to the real content bounds after cleanup.

Sequential write steps:
For each brand, complete all steps before moving to the next brand.

1. Read all child documentation items in the brand section.
2. Build a mapping from documentation item token properties to semantic variable paths.
3. Compare that mapping against the brand extension's recorded overrides.
4. Report before writing that brand:
   - brand name
   - original documented item count
   - planned keep count
   - planned delete count
   - raw override count
   - recorded override count
5. If the batch write constraint is satisfied, proceed with that brand's write without asking again.
6. Delete only documentation items whose semantic variable is not effectively overridden.
7. For kept instances:
   - set final override state first
   - then update exact exposed alias/token display properties
8. Remove empty containers and orphan headings.
9. Resize the target section to content bounds.
10. Verify that brand before continuing to the next brand.

Verification per brand:
1. Take a screenshot of the updated brand section with `figma_capture_screenshot`.
2. Compare visually against the completed examples:
   - only overridden variables remain
   - alias/token display names reflect the brand extension values
   - overridden states are visible
   - spacing and alignment are intact
   - no empty rows, blank cards, empty groups, or orphaned headings remain
3. Directly verify every remaining documented token maps to a recorded override in `extensionCollection.variableOverrides`.
4. Directly verify every visible alias/token display value against:
   `await baseVariable.valuesByModeForCollectionAsync(extensionCollection)`
5. Alias verification must happen after all variant/state updates are complete.
6. For every remaining overridden token, compare the expected resolved display value to the actual exposed alias property:
   - Combo swatch surface token must match exact `Surface alias#...`
   - Combo swatch on-surface token must match exact `On-surface alias#...`
   - Non-combo cards must match exact `Alias token#...`
7. If any alias mismatch remains, fix it and rerun the alias verification before considering the brand complete.
8. Confirm every remaining override-capable component has an overridden visual state:
   - Combo swatch is not `None`
   - Token, typography, foreground, and border cards are `TRUE`
9. Confirm no empty documentation containers remain.
10. Report:
   - number of original documented items inspected
   - number deleted as non-overridden
   - number kept as overridden
   - alias mismatch count after final correction, which must be `0`
   - any unmatched doc items or ambiguous token paths
   - screenshot verification result

Final report:
After all listed brands are complete, report a compact summary table:
- Brand
- Original items
- Deleted
- Kept
- Raw overrides
- Effective overrides
- Redundant overrides excluded
- Final alias mismatches
- Verification result

Important:
- These are destructive Figma writes because documentation items are deleted.
- This prompt grants permission to proceed brand-by-brand only when the batch write constraint is satisfied.
- Stop and ask before writing a brand if any constraint fails.
- Do not write to any channel file.
- Do not use the official remote Figma MCP for governance writes.
- Do not create repo export snapshots unless explicitly requested.
- Do not create a decision log unless a governance exception or non-obvious mapping choice is approved during the work.
```
