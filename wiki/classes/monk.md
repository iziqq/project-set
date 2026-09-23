# Monk

> Zdroje: [raw/2026-09-23-monk](../../raw/2026-09-23-monk.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md), [Paladin](paladin.md)

## Role
| Spec | Role | Mastery |
|---|---|---|
| **Iron Turtle** | Tank | štít z vlastního poškození |
| **Deadly Tiger** | DPS | bonus podle ceny schopnosti v energy |

## Resource
**Energy** (max. 100). Regeneruje se **+5 za 3 s**, ne přes Spirit (Spirit 0).

## Base staty
| Stat | Iron Turtle | Deadly Tiger |
|---|---|---|
| HP | 18 bodů (= 90 životů) | 16 bodů (= 80 životů) |
| Strength | 9 | 8 |
| Agility | 6 | 9 |
| Intelligence / Spirit | 0 (?) | 0 (?) |

## Priorita primary statu (dropy)
**Strength** nebo **Agility**.

## Mastery

### Iron Turtle (tank): Štít z poškození
- **10 % poškození, které Iron Turtle způsobí**, se změní na **štít** (absorb) na Monkovi, trvání **6 s**.
- Každý bod Mastery přidá **+0,5 %**.

```
shield% = 10 % + 0,5 % × Mastery
```
| Mastery | Podíl na štít |
|---|---|
| 0 | 10 % |
| 10 | 15 % |
| 50 | 35 % |
| 100 | 60 % |

**Chování štítu** (jiné než [Paladinův štít](paladin.md#healer-štít-z-healu), viz [štíty](../mechanics/shields.md)):
- **Nesčítá se.**
- Nový štít **větší** než současný → **přepíše** ho (a trvání začne znovu).
- Nový štít **menší** → jen **obnoví trvání** na 6 s.

### Deadly Tiger (DPS): Poškození za energy
- Každý bod Mastery zvýší poškození schopnosti o **0,1 % za každý bod energy**, který schopnost stojí.
- Příklad: 10 Mastery = 1 % za energy → schopnost za 30 energy má **+30 %** poškození.

```
dmgBonus = 0,1 % × Mastery × cenaSchopnosti(energy)
```
| Mastery | Schopnost za 10 | za 30 | za 50 |
|---|---|---|---|
| 10 | +10 % | +30 % | +50 % |
| 50 | +50 % | +150 % | +250 % |
| 100 | +100 % | +300 % | +500 % |

Záměr: odměňuje drahé schopnosti, nevýhodou je jejich cena a nutnost regenerace.
Škálování je strmé (100 Mastery, schopnost za 50 → +500 %). Uživatel to bude ladit později.

## Schopnosti
_Doplnit._

## Otevřené otázky
- Mastery Deadly Tigera škáluje strmě u drahých schopností. Uživatel počítá s pozdějším doladěním.
- Schopnosti.
