# RICE integration contract

## Purpose

RICE: Auvergne is a **flavor submod**, not a map mod and not a France overhaul.

The technical baseline is:

```text
Crusader Kings III vanilla
        +
RICE
        +
RICE: Auvergne
```

The submod must remain useful on the normal vanilla map and should follow RICE's additive scripting style closely enough that individual features could later be proposed upstream.

## Hard rules

### 1. No map changes

Do not add, remove, split, rename, or reposition provinces or baronies.

Do not edit:

- landed title structure for geographic redesign;
- province map data;
- de jure borders;
- holding locations;
- terrain map files.

Historical places such as Saugues or Mercœur are represented through the closest existing vanilla title scopes, character/dynasty content, modifiers, decisions, and events.

### 2. No vanilla file replacement unless unavoidable

Prefer new files under the normal CK3 script folders.

Avoid:

- `replace_path`;
- copied vanilla files with small edits;
- copied RICE files with small edits;
- direct overwrite of RICE events or decisions.

If a future feature appears to require an overwrite, document the reason before implementation and first look for an additive scripted trigger/effect/on_action solution.

### 3. RICE is a dependency, not vendored code

Do not copy generic RICE helpers or art into this repository merely for convenience.

When a stable RICE helper is appropriate, call it directly. Example already used by the submod:

```text
RICE_is_available_adult_even_if_sick_trigger = yes
```

The dependency is declared in `descriptor.mod`.

### 4. Follow RICE script structure

Decisions should normally follow the same major blocks used by RICE:

```text
picture
decision_group_type
ai_check_interval_by_tier
desc
is_shown
is_valid
is_valid_showing_failures_only
effect
cost
ai_potential
ai_will_do
```

Events should follow RICE conventions:

```text
namespace = auvergne

auvergne.X = {
    type = character_event
    title = ...
    desc = ...
    theme = ...
    portraits/scopes when useful
    option = { ... }
    after = { ... }
}
```

When historical context text is useful, respect the RICE game rule:

```text
if = {
    limit = {
        has_game_rule = RICE_historical_context_on
    }
    custom_description_no_bullet = {
        text = auvergne.X.info
    }
}
```

### 5. Namespace ownership

Project-owned database/script keys use `AUV_`.

Project events use:

```text
namespace = auvergne
```

Do not define new keys beginning with `RICE_` unless code is being prepared specifically for an upstream RICE contribution.

## Geographic interface with vanilla

The submod works with vanilla title scopes rather than trying to reproduce medieval territories exactly.

Current working scopes include:

- `d_auvergne` — broad Auvergne anchor;
- `c_auvergne` — core Auvergne;
- `c_clermont_sur_allier` — Clermont-area content where appropriate;
- `c_thiers` — eastern Auvergne content where appropriate;
- `c_velay` — Velay and the northern side of the Upper Allier network;
- `c_gevaudan` — Gévaudan and the southern side of the Upper Allier/Margeride network.

These scopes are **gameplay interfaces**, not claims that vanilla county borders precisely reproduce historical jurisdictions.

In particular, Saugues and the Mercœur lordship should normally be represented by content conditional on `c_velay`, `c_gevaudan`, relevant rulers, dynasties, or local modifiers rather than by introducing a new county/barony.

## Layering model

### Layer A — Vanilla interface

Use existing:

- titles;
- counties;
- cultures;
- faiths;
- traits;
- buildings;
- activities;
- travel systems.

### Layer B — RICE interface

Use compatible RICE:

- helper triggers/effects where stable and relevant;
- historical-context game rule;
- shared art where appropriate and permitted by dependency loading;
- design conventions and balancing patterns.

### Layer C — Auvergne content

Add only project-owned:

- decisions;
- events;
- modifiers;
- scripted triggers;
- scripted effects;
- localization;
- later, project-owned art assets.

## Feature test

Before implementing a proposed feature, ask:

1. Can it work on the existing vanilla map?
2. Can it be expressed with additive files?
3. Does it need to know about RICE, or merely coexist with it?
4. Can a RICE helper be reused rather than copied?
5. Does it represent historical influence proportionally?
6. Would the feature still make sense if Saugues, Mercœur, Clermont, or another historical place is represented only indirectly by a vanilla county?

If the answer to 1 or 2 is no, the feature should normally be redesigned.

## First implemented pattern

`AUV_secure_upper_allier_routes_decision` is the reference implementation for the initial architecture:

- uses only existing vanilla county scopes (`c_velay`, `c_gevaudan`);
- uses a vanilla decision illustration already referenced by RICE;
- uses the RICE adult-availability helper trigger;
- applies only an AUV-owned county modifier;
- triggers only an AUV-owned event;
- uses the RICE historical-context game rule;
- makes no map/history/de-jure changes.

Future early features should stay at approximately this compatibility level until the architecture has been tested in-game.
