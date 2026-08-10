# Tier 1 vertical slice

## Scope

This slice connects three early modules without changing the vanilla map:

1. **Counts and Crosiers** — a repeatable settlement of comital and ecclesiastical authority around Clermont;
2. **The Divided House** — a one-time dynasty state that records either unity or competing comital claims after 1100;
3. **Lords of the High Country** — three distinct approaches to the Upper Allier corridor: investment, toll enforcement, or mediated local rights.

The implementation was aligned against RICE upstream commit `c1e8eb00ee8668b164692875d4c9d631cb895472` (8 August 2026).

This is not the whole Tier 1 backlog. The recurring **Saints and Patrons** loop now covers the two institutions for which the current notes support precise early mechanics: Brioude and La Chaise-Dieu. Aurillac remains deferred pending institution-specific research.

## Evidence boundary

### Counts and Crosiers

Supported by `docs/research/03_centers_and_institutions.md`:

- the bishops of Clermont were major political actors;
- Étienne II belonged to a local aristocratic network and acted in regional politics;
- ecclesiastical authority could participate in peace-making and public order.

The three precise settlements offered by `auvergne.1000` are **Class C gameplay fiction** representing that documented structural rivalry. They are not presented as a specific historical compact.

### The Divided House

Supported by `docs/research/02_dauphins_mercoeur.md`:

- the comital house divided between two Guillaumes in the twelfth century;
- the elder line retained the comital title;
- the younger line's descendants gradually adopted the Dauphin identity.

The slice begins in 1100 and stores the player's choice as a dynasty modifier. It does not create a title, rename a title, generate a cadet branch, select a historical character, or prescribe a territorial partition.

### Lords of the High Country

Supported by `docs/research/01_mercoeur_saugues.md`:

- the Saugues area belonged to a frontier network connected to Mercœur;
- fortified sites structured settlement and controlled access along the Allier and its tributaries;
- ecclesiastical networks were an important part of Mercœur's historical character.

The three policies in `auvergne.2000` are **Class C gameplay fiction** grounded in those documented structures.

### Saints and Patrons

Supported by `docs/research/03_centers_and_institutions.md`:

- Saint-Julien of Brioude was a major aristocratic and canonical center in the Carolingian period;
- its cartulary preserves an exceptional body of ninth- and tenth-century evidence;
- the chapter had a strongly aristocratic character;
- La Chaise-Dieu was founded by Robert of Turlande in 1043 and expanded rapidly within the eleventh-century reform movement.

The patronage offers and follow-up conversations are **Class C gameplay fiction** representing documented institutional functions. La Chaise-Dieu is unavailable before 1043. No Aurillac mechanic has been added because the current research note establishes its priority but does not yet provide an institution-specific anchor comparable to Brioude or La Chaise-Dieu.

## Technical interfaces

- `AUV_controls_clermont_scope_trigger` anchors Clermont content to existing `c_auvergne` and `c_clermont_sur_allier` scopes.
- `AUV_comital_house_compact_modifier` and `AUV_divided_house_foundation_modifier` are the persistent dynasty states for future succession content.
- `AUV_upper_allier_routes_modifier`, `AUV_upper_allier_tolls_modifier`, and `AUV_upper_allier_compact_modifier` are mutually exclusive ten-year county outcomes.
- `AUV_patronize_auvergnat_institution_decision` uses RICE's religious decision group and a native ten-year cooldown; its institution modifiers provide the recurring patronage state.
- `cp:councillor_court_chaplain` represents the ruler's accessible ecclesiastical interlocutor; it is a gameplay abstraction, not a claim that the character is always the historical bishop of Clermont.
- `RICE_is_available_adult_even_if_sick_trigger` and `RICE_historical_context_on` are the only direct RICE helper interfaces used in this slice.

## Research TODOs before deeper mechanics

- **TODO — Clermont offices:** verify how the bishops' temporal lordship and comital jurisdiction changed across the bookmarks before adding date-specific outcomes or named bishops.
- **TODO — comital partition:** establish the exact chronology and territorial content of the division between Guillaume the Elder and Guillaume the Younger before scripting claims, wars, or title transfers.
- **TODO — Dauphin identity:** verify the chronology of diplomatic usage and the maternal naming connection before creating a formal adoption event or title presentation.
- **TODO — CK3 genealogy:** audit vanilla and RICE character/dynasty history at supported bookmarks before targeting named members or automatically creating cadet branches.
- **TODO — Mercœur inheritance:** obtain stronger scholarly evidence before implementing any later transfer of Mercœur to the Dauphin line.
- **TODO — local mapping:** validate the gameplay use of `c_velay` and `c_gevaudan` in-game before attaching rarer Saugues-specific events.
- **TODO — Aurillac:** add an institution-specific scholarly anchor for Saint-Géraud, its patronage networks, and appropriate chronology before exposing it as a patronage choice.
- **TODO — Brioude mapping:** verify the most appropriate vanilla county/barony interface before applying future county-level effects; the present slice deliberately keeps Brioude patronage on the character and dynasty.

## In-game validation checklist

- decision visibility for rulers holding each supported county independently and through a higher-tier title;
- correct resolution of `c_clermont_sur_allier`, `c_auvergne`, `c_velay`, and `c_gevaudan` in `error.log`;
- availability and portrait scoping of `cp:councillor_court_chaplain`;
- dynasty modifier application and one-time gating of the succession decision;
- ten-year expiry and mutual exclusion of county/character modifiers;
- cancellation of delayed `auvergne.1001` when its triggering modifier is no longer present;
- English and French localization parsing, including apostrophes and accented characters;
- availability of the two RICE decision illustrations through the declared dependency.
- ten-year cooldown, pre-1043 hiding of La Chaise-Dieu, and delayed patronage follow-ups;
- availability of the monastery decision illustration through vanilla/RICE dependency loading.
