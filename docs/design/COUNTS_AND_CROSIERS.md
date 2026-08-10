# Counts and Crosiers

## Purpose

`Counts and Crosiers` is the primary political flavor module for Clermont and core Auvergne.

Its purpose is not to simulate a permanent constitutional conflict between a clearly defined count and bishop. Instead, it represents a documented structural fact: comital, episcopal, aristocratic, and ecclesiastical authority overlapped, and religious institutions could participate directly in public order, mediation, political legitimacy, and elite networks.

The module should therefore produce stories about **who can make peace, judge disputes, confirm rights, and turn a written privilege into practical authority**.

## Vanilla/RICE interface

The module must remain additive.

Current gameplay interface:

- existing vanilla Clermont/Auvergne title scopes;
- `cp:councillor_court_chaplain` as a temporary ecclesiastical interlocutor abstraction;
- AUV-owned character/county modifiers;
- AUV-owned events and decisions;
- `RICE_is_available_adult_even_if_sick_trigger`;
- `RICE_historical_context_on`.

The court chaplain is **not** asserted to be the historical bishop of Clermont. A future improvement may resolve an appropriate landed cleric or named historical bishop if this can be done reliably without changing vanilla history or creating brittle title assumptions.

## Current chain

### `auvergne.1000` — The Count and the Crosier

The ruler chooses a ten-year political settlement:

1. confirm ecclesiastical privileges;
2. assert comital jurisdiction;
3. negotiate a written compromise.

These settlements are Class C gameplay reconstructions grounded in documented overlapping authority.

### `auvergne.1001` — The Terms Are Tested

Five to eight years later, the settlement is described as a lived political arrangement rather than a one-click bonus.

For games between 975 and 1100, this can lead to a Peace of God flavor event.

### `auvergne.1002` — An Oath Against Private War

A representative peace oath asks how the ruler responds to ecclesiastical attempts to restrain aristocratic violence.

The player can:

- support ecclesiastical proclamation of the peace;
- insist that public peace derives from comital justice;
- when operating under the negotiated settlement, place the oath under both ecclesiastical and comital authority.

This event does **not** reproduce a specific documented council at Clermont. It represents the late tenth- and eleventh-century political-religious environment associated with the Peace of God in Auvergne.

## Design rules for future events

New `Counts and Crosiers` events should normally involve a concrete problem rather than another abstract choice of bonuses.

Good subjects include:

- sanctuary and pursuit of an accused person;
- competing claims over tolls, markets, or jurisdiction;
- a noble feud reaching an ecclesiastical mediator;
- confirmation or reinterpretation of an old charter;
- aristocratic relatives seeking ecclesiastical office;
- protection of church property during local violence;
- disputes where written privilege and practical possession diverge;
- the foundation of Montferrand in the appropriate twelfth-century context, after specific research.

Avoid:

- a permanent `count vs bishop` meter with no historical actors;
- treating the court chaplain as literally the bishop of Clermont in localization;
- making every ecclesiastical choice simply grant Piety;
- making every comital choice simply grant Tax;
- using the Peace of God outside an appropriate chronology without a separate historical rationale;
- inventing named councils, charters, or jurisdictional settlements.

## Next research gates

Before introducing named or office-specific content, verify:

1. bishops of Clermont represented in supported CK3 bookmarks;
2. whether vanilla provides a reliable landed ecclesiastical scope that can stand for Clermont's episcopal authority;
3. chronology of episcopal temporal lordship and comital jurisdiction;
4. specific eleventh- and twelfth-century disputes suitable for event chains;
5. Montferrand's foundation and its relationship to the comital/episcopal rivalry.

## Gameplay target

A successful Clermont playthrough should not merely produce modifiers. Over several decades the player should remember situations such as:

- having confirmed church rights and later needing clerical mediation;
- having asserted comital justice and then confronted religious claims to make peace;
- having negotiated a compromise that becomes precedent in a later dispute;
- discovering that authority in Auvergne comes from relationships and accepted practice, not only from possession of a title.
