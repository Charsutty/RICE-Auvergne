# Changelog

## 0.0.2 — RICE integration baseline

- Formalized the submod as a strict vanilla-map, additive RICE extension.
- Added `docs/design/RICE_INTEGRATION.md` with compatibility and scripting rules.
- Reworked scripted triggers to use existing vanilla title scopes only.
- Added the first active decision: **Secure the Roads of the Upper Allier**.
- Added the first active event in the Mercœur/Saugues/highland frontier range.
- Added `AUV_upper_allier_routes_modifier`.
- Reused RICE's `RICE_is_available_adult_even_if_sick_trigger` helper.
- Added support for RICE's historical-context game rule in the first event.
- Added complete English and French localization for the first gameplay slice.
- Used an existing vanilla decision illustration whose path is already used by RICE.
- Explicitly prohibited map, province, de jure, and `replace_path` changes as the normal project architecture.

## 0.0.1 — Research scaffold

- Initialized CK3/RICE submod descriptor.
- Established `AUV_` key prefix and `auvergne` event namespace.
- Added English and French localization scaffolds.
- Added decision, trigger, effect, and event scaffolds.
- Added historical research methodology.
- Added initial research notes on Mercœur/Saugues, the Dauphins of Auvergne, and major regional centers.
- Added project scope, credits, and art provenance policy.
