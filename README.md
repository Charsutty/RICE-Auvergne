# RICE: Auvergne

A historical flavor submod for **Crusader Kings III** and **RICE (Regional Immersion and Cultural Enrichment)**, focused on medieval Auvergne and its connected highland worlds: Clermont, Brioude, Aurillac, La Chaise-Dieu, the Velay, Mercœur, Saugues, and the northern Gévaudan/Margeride.

## Status

Early development. A first Tier 1 vertical slice now connects Clermont's competing authorities, the technical foundation of the divided comital house, and the Upper Allier highland corridor.

## Core design rule

**This is not a map mod.**

RICE: Auvergne is designed to sit cleanly on top of the normal vanilla CK3 map and RICE. It does not attempt to redraw medieval Auvergne, create a county of Saugues, or reconstruct the sirerie of Mercœur as new landed titles.

Instead, historical places and networks are expressed through existing vanilla titles, characters, events, decisions, modifiers, travel, religious patronage, dynastic relationships, and other additive systems.

The design principle is to represent historical importance proportionally. Saugues and the Margeride are present because they belonged to a documented frontier and seigneurial network dominated in part by the lords of Mercœur, not because the project aims to make them artificially central. Clermont and the major Auvergnat political and ecclesiastical centers remain structurally central.

## Core themes

- Fragmented political authority in medieval Auvergne.
- Counts, Dauphins, bishops, monasteries, castellans, and urban communities.
- The dynasty of Mercœur and its links with the Dauphins of Auvergne.
- Highland lordship, roads, fortifications, pastoralism, and frontier control.
- Major religious networks: Clermont, Brioude, Aurillac, La Chaise-Dieu, and Le Puy.
- Occitan court culture without reducing Auvergne to generic southern-French flavor.

## Content objectives

The pack is organized around six design objectives:

1. represent fragmented political authority;
2. give the comital house and Dauphins a dynamic dynastic history;
3. make major religious institutions political actors;
4. represent the highlands as a social and political system;
5. let Auvergnat identity emerge from gameplay rather than define the mod upfront;
6. keep Auvergne connected to the wider French, Aquitanian, Occitan, monastic, and pilgrimage worlds.

These objectives are implemented through five planned modules: **Counts and Crosiers**, **The Divided House**, **Saints and Patrons**, **Lords of the High Country**, and **Courts of Auvergne**.

See [`docs/design/CONTENT_OBJECTIVES.md`](docs/design/CONTENT_OBJECTIVES.md) for the full content hierarchy, priority tiers, scope rules, and recommended development order.

## Dependency and layering

The intended load stack is:

```text
Crusader Kings III vanilla
        +
RICE
        +
RICE: Auvergne
```

RICE remains an external dependency. Its files should not be copied into this repository merely for convenience.

The submod follows RICE's additive scripting conventions and may directly use stable RICE helpers where appropriate. Project-owned keys use the `AUV_` prefix and events use the `auvergne` namespace.

See [`docs/design/RICE_INTEGRATION.md`](docs/design/RICE_INTEGRATION.md) for the compatibility contract.

## First Tier 1 vertical slice

The first connected implementation includes:

- **Negotiate Authority at Clermont**, a recurring choice between ecclesiastical privileges, comital jurisdiction, and a negotiated compact;
- **Address the Comital Succession**, a post-1100 dynasty-state foundation for the future Divided House chain without prematurely creating a Dauphin title or branch;
- **Patronize an Auvergnat Institution**, a renewable relationship with Saint-Julien of Brioude or, after 1043, La Chaise-Dieu;
- an expanded **Secure the Roads of the Upper Allier**, with investment, toll, and mediated-rights outcomes.

All three use existing vanilla title scopes, additive AUV-owned script, current RICE decision/event conventions, the RICE availability helper, the historical-context game rule, and complete English/French localization. See [`docs/design/TIER1_VERTICAL_SLICE.md`](docs/design/TIER1_VERTICAL_SLICE.md) for evidence boundaries and research TODOs.

## Documentation

Historical research lives under [`docs/research/`](docs/research/). Design decisions distinguish documented facts, plausible reconstruction, and gameplay fiction.

Current historical priorities are:

1. the comital house and emergence of the Dauphins of Auvergne;
2. Mercœur as both a highland lordship and an ecclesiastical/dynastic network;
3. Clermont, Brioude, Aurillac, and La Chaise-Dieu as major political or religious anchors;
4. the Upper Allier, Saugues, Velay, and northern Gévaudan as connected secondary flavor rather than an artificial new principality.

## Art

DDS and other project-owned art assets will be handled in a later dedicated pipeline. Until then, early gameplay should prefer existing vanilla/RICE-compatible illustrations whose paths are already verified in RICE.
