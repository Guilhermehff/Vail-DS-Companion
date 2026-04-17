# Decision Log

- Date: 2026-04-16
- Title: Remove Shared Status Color Lanes From the Active Token Model
- Status: accepted
- Scope: color governance
- Brand (if brand-specific):
- Figma file (if applicable): https://www.figma.com/design/70O01X6MWNKMpsLqIke99Q/Foundations%20-%20Resorts?node-id=265-2899
- Stakeholders: Design System Governance
- Supersedes:
  - figma/decisions/2026-03-13-proposed-semantic-role-channel-color-model.md
- Superseded by:

## Context

The active Foundations file was simplified in live Figma by removing the shared semantic status lanes and the raw yellow and red families that only existed to support them. The runtime inventory now shows:

- `_Global: Color` still contains `universal/green/100-900`
- `_Global: Color` no longer contains `universal/yellow/*` or `universal/red/*`
- `Semantic: Theme` no longer contains any `positive`, `warning`, or `critical` tokens

That live state conflicts with the current repo taxonomy and color guidance, which still describe shared status roles as part of the active semantic contract.

## Decision

1. Remove shared `positive`, `warning`, and `critical` lanes from the active semantic theme model.
2. Remove raw yellow and red status-support ramps from the active global color model.
3. Keep `universal/green/100-900` in `_Global: Color` as a raw family only. Its continued presence does not imply an active semantic status lane.
4. Restrict the active semantic color model to:
   - neutral role sets
   - `brand`
   - `brand_secondary`
   - inverse companions
   - governed asset tokens
5. Treat any future reintroduction of shared status semantics as a new governance decision rather than an inherited part of the model.

## Scope

- Affected collections:
  - `_Global: Color`
  - `Semantic: Theme`
- Affected tokens or artifact paths:
  - `figma/config/variable-taxonomy.yml`
  - `figma/docs/brand-color-foundations.md`
  - `figma/templates/brand-color-preview.md`
  - historical decisions that described status lanes as active governance
- Explicit exceptions:
  - `universal/green/100-900` remains a governed raw family in `_Global: Color`
- Inherited or deferred items:
  - channel-specific status handling is deferred and must be defined in a future channel or semantic decision if needed
  - historical records describing the removed status model remain as history, not active taxonomy

## Consequences

The active repo contract now matches the live Figma file: semantic theme colors no longer include shared status lanes, and raw green remains available without semantic meaning attached to it. Brand review and preview artifacts should no longer imply that `positive`, `warning`, or `critical` are part of the current semantic mapping set.

Any downstream work that needs notices, alerts, or validation states must either:

- solve them in a channel-specific layer, or
- introduce a new approved semantic decision first

## Follow-up

- Update:
  - remove status-lane references from the active taxonomy and color guidance
- Link from:
  - this decision stands as the current active color-governance record for status-lane removal
- Verify:
  - live Figma runtime inventory for `_Global: Color` and `Semantic: Theme`
