# Cleric

> Zdroje: [raw/2026-09-23-cleric](../../raw/2026-09-23-cleric.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md), [Shaman](shaman.md)

## Speky
| Spec | Role | Styl |
|---|---|---|
| **Mind Bender** | DPS | debuff **Insane**: cíl dává míň poškození a dostává víc |
| **Prophet** | Healer | primárně **buffer** — zesiluje ostatní postavy |
| **Bishop** | Healer | klasický heal s **Echo** (heal skáče na druhý cíl) |

## Resource
**Mana** (max. 100)

## Base staty
| Stat | Mind Bender | Prophet | Bishop |
|---|---|---|---|
| HP | 16 bodů (= 80 životů) | 18 bodů (= 90 životů) | 16 bodů (= 80 životů) |
| Intelligence | 10 | 4 | 8 |
| Spirit | 7 | 11 | 9 |
| Strength / Agility | 0 (?) | 0 (?) | 0 (?) |

Prophet má **nejvyšší Spirit ze všech postav** (11) a nejnižší Intelligence (4) — nehealuje ani
nedamaguje, buffuje.

## Priorita primary statu (dropy)
Jen **Intelligence**.

## Mastery

### Mind Bender: Insane
Každý zásah aplikuje na cíl stack debuffu **Insane**, **max. 3 stacky**.
- **Redukce poškození cíle** = **5 % za stack**, Mastery ji zvyšuje o **0,1 % za bod**,
  **max. 13,3 % za stack** (3 stacky = 39,9 %, prakticky 40 %).
  Strop je dosažen při **83 Mastery**.
- **Bonus poškození do cíle** = **0,1 % za bod Mastery za každý stack**.
- **Trvání stacku 30 s**, každá další aplikace obnoví trvání na 30 s.

```
redukce/stack = min(5 % + 0,1 % × Mastery, 13,3 %)
redukceCelkem = stacky × redukce/stack           (max. 39,9 % při 3 stacích)
dmgBonus      = stacky × 0,1 % × Mastery
```
| Mastery | Redukce / stack | Redukce (3 stacky) | Bonus dmg (3 stacky) |
|---|---|---|---|
| 0 | 5 % | 15 % | 0 % |
| 50 | 10 % | 30 % | +15 % |
| 83+ | 13,3 % (strop) | 39,9 % | +25 % a výš |
| 200 | 13,3 % (strop) | 39,9 % | +60 % |

Po dosažení stropu redukce roste dál už jen bonus poškození.

### Prophet: Síla buffů
- Každý bod Mastery zvýší **sílu buffů** o **0,1 %**.

| Mastery | Buffy silnější o |
|---|---|
| 50 | +5 % |
| 100 | +10 % |
| 200 | +20 % |

Plánované typy buffů (uživatel ještě domýšlí):
- procentuální **zvýšení poškození** spoluhráčům,
- krátkodobý buff na spoluhráče, který přidává **Holy Fire** (DoT na zasažené cíle),
- **aura** kolem Propheta s mírným healem.

### Bishop: Echo
- Každý heal se **odrazí (Echo)** na **druhý cíl s nejnižším procentem HP**.
- Síla Echa = **0,5 % za bod Mastery** z původního healu, **max. 60 %** (= 120 Mastery).
- Echo může skočit i **zpět na hlavní cíl** (např. když je zraněný jen jeden hráč).

| Mastery | Echo |
|---|---|
| 20 | 10 % |
| 60 | 30 % |
| 120+ | 60 % (strop) |

## Schopnosti
_Doplnit._

## Otevřené otázky
- **Insane:** platí redukce i proti ostatním hráčům (PvP)?
- **Prophet:** konkrétní seznam buffů, aury a jejich hodnot (uživatel domýšlí).
- **Bishop:** spouští Echo další Echo? (Návrh (?): ne.)
- Schopnosti.
