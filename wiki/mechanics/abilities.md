# Schopnosti (abilities)

> Zdroje: [raw/2026-09-23-schopnosti-rozsah](../../raw/2026-09-23-schopnosti-rozsah.md) · Související: [classes](classes.md), [staty](stats.md), [talenty](talents.md)

## Rozsah
- **5–6 aktivních schopností** na postavu (?) — záměrně málo, aby hra nebyla složitá.
- K tomu **několik pasivních schopností** (např. [Ignite](../classes/wizard.md#pyromancer-ignite),
  [Bleed](../classes/warrior.md#bleed-dancer-dps-bleed) — Mastery efekty jsou pasivky).
- Kromě toho **autoattack** (u Warriora generuje Rage, viz [staty](stats.md#resource-enum)).

## Šablona schopnosti
Každá schopnost se popisuje stejnými poli:

| Pole | Popis |
|---|---|
| **Název** | |
| **Typ** | aktivní / pasivní |
| **Cena** | kolik resource stojí (Mana / Rage / Energy) |
| **Cooldown** | v sekundách, snižuje ho [CDR](stats.md#cooldown-reduction) |
| **Cast time** | okamžitá, nebo sesílání X s (?) |
| **Dosah** | z [Range zbraně](equipment.md#range-zbraní), nebo vlastní |
| **Cíl** | nepřítel / spoluhráč / sám / plocha |
| **Efekt** | poškození nebo heal + škálování ze statu (např. 100 % Str), další efekty |

Příklad zápisu:
> **Shield Bash** — aktivní · 20 Rage · CD 8 s · okamžitá · melee · 1 nepřítel ·
> 150 % Strength fyzického poškození, stun 1 s. Vyžaduje štít.

## Otevřené otázky
- **5–6 schopností na postavu, nebo na spec?** Sdílí speky jedné postavy schopnosti (Warden
  i Bleed Dancer mají stejný základ), nebo má každý spec vlastní sadu?
- Kolik schopností je na hotbaru naráz? Dá se sada měnit, nebo jsou všechny pořád dostupné?
- Mají schopnosti globální cooldown?
- Odemykají se schopnosti postupně během běhu, nebo je má postava od začátku?
- Mění talenty schopnosti, nebo jen jejich hodnoty?
