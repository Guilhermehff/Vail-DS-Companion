# Liberty Mountain Color Preview

Review state: written in figma. Verify live write state in `figma/brands/liberty_mountain/brand.yml` and Figma.

## Original Source Swatches

- Source color: `Twilight`
  Provided value: `#3f5364`
- Source color: `Summit`
  Provided value: `#748693`
- Source color: `Tundra`
  Provided value: `#3a4959`
- Source color: `Shale`
  Provided value: `#51879f`
- Source color: `Stone`
  Provided value: `#4e5758`
- Source color: `Sand`
  Provided value: `#b8b09b`
- Source color: `Mineral`
  Provided value: `#d7d2cb`
- Source color: `Limestone`
  Provided value: `#ebe7e3`
- Source color: `Sunrise`
  Provided value: `#ff5a34`
  Notes: Preserved as source provenance only. Not a live raw family in Figma.
- Source color: `Sunset`
  Provided value: `#e18431`
- Source color: `Flora`
  Provided value: `#6a1f45`
  Notes: Preserved as source provenance only. Not a live raw family in Figma.
- Source color: `Spring`
  Provided value: `#b8bf09`
  Notes: Preserved as source provenance only. Not a live raw family in Figma.
- Source color: `Copper`
  Provided value: `#9d5f15`
  Notes: Preserved as source provenance only. Not a live raw family in Figma.

## Live Raw Families

- `liberty_mountain/cool_neutral/*`
- `liberty_mountain/warm_neutral/*`
- `liberty_mountain/shale/*`
- `liberty_mountain/stone/*`
- `liberty_mountain/sunset/*`

## Review Notes

- Live Figma now carries five Liberty Mountain raw color families instead of the earlier nine-family repo snapshot.
- `sunrise`, `spring`, `flora`, and `copper` are preserved as source provenance only and are no longer live raw families.
- The shared semantic neutral role set remains inherited from the base collection.

## Live Semantic Mapping

- `color/surface/neutral/*`, `color/on_surface/neutral/*`, `color/foreground/default`, `color/foreground/subtle`, `color/border/default`, `color/border/subtle` -> `inherited_base`
  The live semantic neutral role set remains inherited from the base collection.
- `color/surface/brand/*`, `color/on_surface/brand/*`, `color/foreground/brand`, `color/border/brand` -> `liberty_mountain/cool_neutral`
  The live expressive brand lane now resolves through `cool_neutral`, with default and strong surfaces on `cool_neutral/700` and `cool_neutral/800`.
- `color/surface/brand_secondary/*`, `color/on_surface/brand_secondary/*`, `color/foreground/brand_secondary`, `color/border/brand_secondary` -> `liberty_mountain/warm_neutral`
  The live expressive secondary lane now resolves through `warm_neutral`, with default and strong surfaces on `warm_neutral/300` and `warm_neutral/500`.
- Global-only families: `liberty_mountain/shale`, `liberty_mountain/stone`, `liberty_mountain/sunset`
- `variables/assets/logo` -> `Liberty Mountain`

## Review Readiness

- Subject: `Liberty Mountain live lane mapping`
  Channels: `web, email, ads`
  Rule: Treat `cool_neutral` as the live expressive brand lane and `warm_neutral` as the live expressive secondary lane until a newer governance decision changes the semantic mapping.
  Source basis: Live Figma semantic extension state.

- Subject: `Liberty Mountain removed raw families`
  Channels: `web, email, ads`
  Rule: Do not treat `sunrise`, `spring`, `flora`, or `copper` as live `_Global: Color` families.
  Source basis: Live Figma `_Global: Color` inventory.
