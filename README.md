# RICE: Auvergne

A historical flavor submod for **Crusader Kings III** and **RICE (Regional Immersion and Cultural Enrichment)**, focused on medieval Auvergne and its connected highland worlds: Clermont, Brioude, Aurillac, La Chaise-Dieu, the Velay, Mercœur, Saugues, and the northern Gévaudan/Margeride.

## Status

Early research and project scaffolding.

The design principle is to represent historical importance proportionally. Saugues and the Margeride are present because they belonged to a documented frontier and seigneurial network dominated in part by the lords of Mercœur, not because the project aims to make them artificially central. Clermont and the major Auvergnat political and ecclesiastical centers remain structurally central.

## Core themes

- Fragmented political authority in medieval Auvergne.
- Counts, Dauphins, bishops, monasteries, castellans, and urban communities.
- The dynasty of Mercœur and its links with the Dauphins of Auvergne.
- Highland lordship, roads, fortifications, pastoralism, and frontier control.
- Major religious networks: Clermont, Brioude, Aurillac, La Chaise-Dieu, and Le Puy.
- Occitan court culture without reducing Auvergne to generic southern-French flavor.

## Dependency

This project is designed as a **RICE submod**. RICE remains an external dependency; its files and assets should not be copied unless technically necessary and explicitly permitted.

## Namespaces

All project-owned script keys should use `AUV_` and event IDs should use the `auvergne` namespace.

## Documentation

Historical research lives under [`docs/research/`](docs/research/). Design decisions should distinguish documented facts, plausible reconstruction, and gameplay fiction.

## Current scope

The first implementation target is a vertical slice around:

1. Clermont and comital/episcopal authority;
2. Mercœur, Saugues, and frontier lordship;
3. Aurillac / Brioude / La Chaise-Dieu as religious and aristocratic networks.

DDS and other art assets will be handled in a later dedicated pipeline.
