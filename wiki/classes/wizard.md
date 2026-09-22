# Wizard

> Zdroje: [raw/2026-09-22-wizard](../../raw/2026-09-22-wizard.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md)

## Role
Jen **DPS**, se dvěma variantami (volí se při výběru postavy):
- **Pyromancer**: oheň, DoT (Ignite), šíření mezi cíli
- **Soultaker**: poškození roste s počtem nepřátel, „master blaster“ na hordy malých nepřátel

## Resource
**Mana** (max. 100)

## Base staty
| Stat | Hodnota |
|---|---|
| HP | 14 bodů (= 70 životů) |
| Intelligence | 15 |
| Spirit | 4 (= 4 % regenerace many za sekundu) |
| Strength / Agility | 0 (?) |

## Priorita primary statu (dropy)
Jen **Intelligence**.

## Mastery

### Pyromancer: Ignite
Pasivní schopnost **Ignite**: každé poškození, které Wizard způsobí, zapálí cíl.
Záměr: **multi-target** postava. Oheň se může postupně rozhořet na celou skupinu. Síla se doladí přepočtem.

- **Ignite (celkem)** = **(10 % + 0,5 % × Mastery) × poškození zásahu**, rozložené do 4 ticků
  (každých **0,5 s** po dobu **2 s**). Bez Mastery = **2,5 % za tick**.
- **Opakovaný zásah** funguje stejně jako [Warrior bleed](warrior.md#dps-bleed): první zásah
  nastaví plnou hodnotu, každý další přičte 50 % nově aplikovaného Ignite a obnoví trvání na 2 s.
  Vlastní tick timer, při vypršení mezi ticky proběhne částečný tick. Každý Wizard má na cíli vlastní Ignite.

| Mastery | Ignite celkem | Za tick |
|---|---|---|
| 0 | 10 % | 2,5 % |
| 20 | 20 % | 5 % |
| 50 | 35 % | 8,75 % |
| 100 | 60 % | 15 % |

#### Přeskok (spread)
- Šance **1 % × Mastery** se zkouší **při každém ticku** („oheň se rozhoří a pak přeskočí“).
- Ignite **zůstane** na původním cíli a na nový cíl se **zkopíruje zbývající** Ignite (hodnota ticku
  i zbývající čas). Nevzniká nový Ignite z plné hodnoty.
- Přeskakuje se **jen na nepřátele bez Ignite** (v okolí (?)). Když žádný takový není, přeskok nenastane.
  Tím se zabrání cyklickému přeskakování 1 → 2 → 1 a nekonečnému stackování.
- **Řetězení je povolené:** i zkopírovaný Ignite může přeskakovat dál. Protože kopie nese jen
  zbývající čas, každá další generace je kratší a slabší.

### Soultaker: Poškození podle počtu nepřátel
Záměr: „master blaster“ proti velkým skupinám malých nepřátel.

- Bonus za každého nepřítele v okolí = **1 % + 0,1 % × Mastery**.
- **Okolí** = poměrně velký okruh kolem Wizarda (hodnota se určí).
- V **PvP** se počítají i nepřátelští hráči. Pro PvP možná vyšší koeficient Mastery, aby byl Soultaker dost silný (?).

```
dmgBonus = početNepřátel × (1 % + 0,1 % × Mastery)
```
| Mastery | Za nepřítele | 5 nepřátel | 10 nepřátel | 20 nepřátel |
|---|---|---|---|---|
| 0 | 1 % | +5 % | +10 % | +20 % |
| 20 | 3 % | +15 % | +30 % | +60 % |
| 50 | 6 % | +30 % | +60 % | +120 % |
| 100 | 11 % | +55 % | +110 % | +220 % |

## Schopnosti
_Doplnit._

## Otevřené otázky
- PvP koeficient Soultaker Mastery (bude-li jiný než v PvE).
- Schopnosti.
