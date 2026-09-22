# Scout

> Zdroje: [raw/2026-09-22-scout](../../raw/2026-09-22-scout.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md)

## Role
Jen **DPS**, ale se **dvěma variantami** (volí se při výběru postavy):
- **Hawkeye**: ranged DPS, střílí z **luku** (luk může nosit **jen Hawkeye**, viz [equipment](../mechanics/equipment.md))
- **Adventurer**: melee DPS

## Resource
**Energy** (max. 100)

## Base staty
| Stat | Hodnota |
|---|---|
| HP | 15 bodů (= 75 životů) |
| Agility | 12 |
| Strength | 6 |
| Intelligence | 0 (?) |

Stejné pro obě varianty.

## Priorita primary statu (dropy)
**Agility** nebo **Strength**.

## Mastery

### Hawkeye (ranged): Poškození ranged zbraní
- Každý bod Mastery zvýší poškození s **ranged zbraní** o **0,3 %**.

| Mastery | Bonus |
|---|---|
| 50 | +15 % |
| 100 | +30 % |
| 200 | +60 % |

### Adventurer (melee): Efektivita Agility
- Každý bod Mastery zvyšuje **efektivitu Agility**. **200 Mastery = +100 %** (Agility dává dvojnásobek).
- Lineárně **+0,5 % za bod**, bez stropu.

```
agilityEffectivity = 1 + 0,005 × Mastery
```
| Mastery | Efektivita | 1 bod Agility dá |
|---|---|---|
| 0 | 100 % | +1 fyz. dmg, +1 Attack Speed, +1 Crit Chance |
| 100 | 150 % | +1,5 / +1,5 / +1,5 |
| 200 | 200 % | +2 / +2 / +2 |

## Schopnosti
_Doplnit._

## Otevřené otázky
- Zesiluje efektivita Adventurera i base Agility? (Návrh: veškerou Agility.)
- Schopnosti.
