# Decision Log

- Date: 2026-05-27
- Title: Semantic theme exception namespaces
- Status: accepted
- Scope: Semantic token naming, exception namespace governance, repo artifact alignment
- Brand (if brand-specific): n/a
- Figma file (if applicable): Foundations - Resorts
- Stakeholders: Design system governance, Foundations maintainers, channel library authors
- Supersedes: 2026-04-06-grouped-semantic-theme-namespaces.md
- Superseded by:

## Context

`Semantic: Theme` needs to remain easy to scan in Figma while supporting more than color and typography. The live collection now includes universal asset selectors, universal component helper tokens, and channel-scoped semantic exceptions for Email and Ads. Treating those families as ad hoc exceptions or forcing them under color- or typography-first paths makes the collection harder to browse and weakens governance clarity.

## Decision

1. Keep `Semantic: Theme` as one shared published collection.
2. Approve five top-level semantic families:
   - `color/*`
   - `typography/*`
   - `assets/*`
   - `components/*`
   - `channel/*`
3. Treat `assets/*`, `components/*`, and `channel/*` as first-class governed semantic namespaces, not informal exceptions.
4. Reserve:
   - `assets/*` for universal semantic asset selectors
   - `components/*` for universal semantic component helper tokens
   - `channel/*` for approved channel-scoped semantic exceptions such as Email and Ads
5. Do not introduce additional top-level semantic families without a new accepted governance decision.

## Scope

- Affected collections:
  - `Semantic: Theme`
- Affected tokens or artifact paths:
  - `/Users/guilhermefidelio/Documents/GitHub/Vail Resorts DS/AGENTS.md`
  - `/Users/guilhermefidelio/Documents/GitHub/Vail Resorts DS/figma/config/variable-taxonomy.yml`
- Explicit exceptions:
  - Historical decision logs may continue to describe the prior `variables/*` exception model when referring to past state.
- Inherited or deferred items:
  - Existing live token names remain valid unless a separate rename decision is accepted.
  - `color/*` and `typography/*` remain the canonical top-level families for semantic color and typography tokens.

## Consequences

The semantic collection can remain readable in Figma without hiding universal assets, universal components, or channel-controlled semantic tokens behind a generic exception namespace. Governance docs must now describe these three families as approved top-level semantic namespaces rather than out-of-model exceptions.

## Follow-up

- Update:
  - Align active governance docs with the five-family semantic namespace model.
- Link from:
  - Future decisions that add new semantic exception subtrees.
- Verify:
  - Canonical repo docs describe `assets/*`, `components/*`, and `channel/*` as approved top-level semantic families.
