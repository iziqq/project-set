# Summoner

> Zdroje: [raw/2026-09-22-summoner](../../raw/2026-09-22-summoner.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md)

Postava, která bojuje pomocí **vyvolaných bytostí**.

## Speky (volí se při výběru postavy)
| Spec | Role | Vyvolání |
|---|---|---|
| **Hell Knight** | Tank | **pekelná stvůra** (démon), která tankuje za něj |
| **Necromancer** | DPS | **1 permanentní kostlivec**, který pomáhá v boji |
| **Warlock** | DPS | mistr vyvolávání **malých démonů na krátkou dobu** |

### Hell Knight
- Tankuje přes démona. Je **méně efektivní tank** než „normální“ tanci (Warrior, Paladin, Monk).
- Kompenzace: Hell Knight **může healovat svého démona**.

## Resource
**Mana** (max. 100)

## Base staty
| Stat | Hell Knight (Tank) | Necromancer / Warlock (DPS) |
|---|---|---|
| HP | 18 bodů (= 90 životů) | 13 bodů (= 65 životů) |
| Intelligence | 10 | 15 |
| Spirit | 5 | 5 |
| Strength / Agility | 0 (?) | 0 (?) |

## Priorita primary statu (dropy)
Jen **Intelligence**.

## Mastery

### Hell Knight: Obrana démona
- Každý bod Mastery převádí část **defenzivních statů** Summonera na démona.
- Démon získá **1 % za bod** ze Summonerova **HP** a **Mitigation** (navíc ke svým vlastním statům).

```
démon.HP         += summoner.HP         × 1 % × Mastery
démon.Mitigation += summoner.Mitigation × 1 % × Mastery
```
| Mastery | Démon dostane navíc |
|---|---|
| 50 | 50 % HP a Mitigation Summonera |
| 100 | 100 % |

### Necromancer: Síla kostlivce
- **+1 % poškození kostlivce** za bod Mastery.

| Mastery | Bonus |
|---|---|
| 50 | +50 % |
| 100 | +100 % |

### Warlock: Trvání démonů
- **+0,1 s trvání** malých démonů za bod Mastery.

| Mastery | Trvání navíc |
|---|---|
| 20 | +2 s |
| 50 | +5 s |
| 100 | +10 s |

## Vyvolané bytosti
Staty, trvání, počet, cena a znovuvyvolání každé bytosti určuje **konkrétní kouzlo nebo pasivní
schopnost**, která ji vyvolává. Např. Warlockovi démoni mají podle kouzla 2 s, 8 s apod.
Upřesní se při návrhu schopností.

## Schopnosti
_Doplnit._

## Otevřené otázky
- **Hell Knight a aggro:** jak démon drží nepřátele na sobě (viz obecná otázka aggro v [classes](../mechanics/classes.md))?
- Ovládá hráč summony (příkazy, cíl), nebo AI? (Může určit schopnost.)
- Schopnosti (včetně parametrů summonů).
