# Schopnosti (abilities)

> Zdroje: [raw/2026-09-23-schopnosti-rozsah](../../raw/2026-09-23-schopnosti-rozsah.md) · Související: [classes](index.md), [staty](../stats/index.md), [talenty](talents.md)

## Rozsah
- **5–6 aktivních schopností** na postavu (?) — záměrně málo, aby hra nebyla složitá.
- **Mastery pasivka**: každý spec má jednu základní pasivku, jejíž sílu zvyšuje stat
  [Mastery](../stats/index.md#mastery)
  (např. Block Chance u Wardena, Bleed u Bleed Dancera). Je popsaná v `abilities.md` dané postavy.
- K tomu **několik dalších pasivních schopností** (např. [Ignite](../classes/wizard/abilities.md#pyromancer-ignite),
  [Bleed](../classes/warrior/abilities.md#bleed-dancer-dps-bleed) — Mastery efekty jsou pasivky).
- Kromě toho **autoattack** (během sesílání kouzla nejde autoattackovat, viz [souboj](../combat/index.md#autoattack))

## Pravidla pro návrh
- **Každý tank spec musí mít AoE schopnost** — bez ní neudrží aggro na skupině
  ([threat](../combat/threat.md)).
- Schopnosti generují threat z poškození a healu; tank spec má 10× vyšší generaci.

## Šablona schopnosti
Každá schopnost se popisuje stejnými poli:

| Pole | Popis |
|---|---|
| **Název** | |
| **Typ** | aktivní / pasivní |
| **Cena** | kolik resource stojí (Mana / Rage / Energy) |
| **Cooldown** | v sekundách, snižuje ho [CDR](../stats/index.md#cooldown-reduction) |
| **Cast time** | okamžitá, nebo sesílání X s (?) |
| **Dosah** | z [Range zbraně](../equipment/index.md#range-zbraní), nebo vlastní |
| **Cíl** | nepřítel / spoluhráč / sám / plocha |
| **Efekt** | poškození nebo heal + škálování ze statu (např. 100 % Str), další efekty |

Příklad zápisu:
> **Shield Bash** — aktivní · 20 Rage · CD 8 s · okamžitá · melee · 1 nepřítel ·
> 150 % Strength fyzického poškození, stun 1 s. Vyžaduje štít.

## Kde jsou konkrétní schopnosti
V `wiki/classes/<postava>/abilities.md`:
[Warrior](../classes/warrior/abilities.md) · [Paladin](../classes/paladin/abilities.md) ·
[Scout](../classes/scout/abilities.md) · [Wizard](../classes/wizard/abilities.md) ·
[Summoner](../classes/summoner/abilities.md) · [Monk](../classes/monk/abilities.md) ·
[Shaman](../classes/shaman/abilities.md) · [Cleric](../classes/cleric/abilities.md)

## Otevřené otázky
- **5–6 schopností na postavu, nebo na spec?** První návrh ([Warrior](../classes/warrior/abilities.md))
  je psaný **na spec** (6 pro Wardena, 6 pro Bleed Dancera) — potvrdit jako pravidlo, nebo část
  schopností sdílet v rámci postavy?
- Kolik schopností je na hotbaru naráz? Dá se sada měnit, nebo jsou všechny pořád dostupné?
- Mají schopnosti globální cooldown?
- Odemykají se schopnosti postupně během běhu, nebo je má postava od začátku?
- Mění talenty schopnosti, nebo jen jejich hodnoty?
