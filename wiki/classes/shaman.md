# Shaman

> Zdroje: [raw/2026-09-23-shaman](../../raw/2026-09-23-shaman.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md)

## Speky
| Spec | Role |
|---|---|
| **Witch Doctor** | Healer — heal vzniká z poškození, které způsobí |
| **Voodoo Master** | DPS — přenáší část poškození na označené cíle |

## Resource
**Mana** (max. 100)

## Base staty
| Stat | Witch Doctor (Heal) | Voodoo Master (DPS) |
|---|---|---|
| HP | 16 bodů (= 80 životů) | 16 bodů (= 80 životů) |
| Intelligence | 8 | 10 |
| Spirit | 9 | 7 |
| Strength / Agility | 0 (?) | 0 (?) |

Witch Doctor má **nejvyšší Spirit ze všech postav** (9), tedy 9 % regenerace many za sekundu.

## Priorita primary statu (dropy)
Jen **Intelligence**.

## Mastery

### Witch Doctor: Heal z poškození
- Když Witch Doctor způsobí poškození, **12 %** z něj se použije jako **heal**.
- **Overheal se neřeší** (přebytek propadne).
- Cíl healu = spoluhráč s **nejnižším procentem HP** (počítá se i **Shaman sám**), v **dosahu**
  (dosah bude dostatečně velký).
- Každý bod Mastery přidá **+0,1 %**.

```
heal% = 12 % + 0,1 % × Mastery
```
| Mastery | Podíl na heal |
|---|---|
| 0 | 12 % |
| 50 | 17 % |
| 100 | 22 % |

### Voodoo Master: Voodoo Doll
- Debuff **Voodoo Doll** se aplikuje **jedním kouzlem** a je **vždy jen na jednom cíli**.
- Trvá, dokud cíl nezemře nebo dokud Shaman neoznačí jiný cíl.
- Cíl s Voodoo Doll dostává **10 %** poškození, které Shaman způsobí **hlavnímu cíli**.
- Když je **hlavní cíl zároveň Voodoo Doll**, žádný přenos se nepočítá.
- Každý bod Mastery přidá **+0,05 %**.

```
přenos% = 10 % + 0,05 % × Mastery
```
| Mastery | Přenos na Voodoo Doll |
|---|---|
| 0 | 10 % |
| 100 | 15 % |
| 200 | 20 % |

## Schopnosti
_Doplnit._

## Otevřené otázky
- Schopnosti.
