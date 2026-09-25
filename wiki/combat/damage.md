# Výpočet poškození

> Související: [staty](../stats/index.md), [štíty](shields.md), [efekty](effects.md)

## Pořadí (návrh (?))
```
1. base poškození schopnosti + bonus ze statů (Str / Agi / Int)
2. modifikátory útočníka (Mastery pasivky, buffy, talenty)
3. hit roll        — hit = 60 % + 2 % × min(body, 20)
4. crit roll       — krit = 120 % (+ Crit Damage, talenty)
5. block           — jen Warden se štítem, jen fyzické poškození
6. Mitigation cíle — redukce = M / (M + 100), fyzické i magické
7. štíty cíle      — absorb, viz shields
8. odečtení z HP
```

## Typy poškození
| Typ | Zdroj | Poznámky |
|---|---|---|
| **Fyzické** | Strength, Agility | jde blokovat ([block](#block)) |
| **Magické** | Intelligence | **nejde blokovat**, Mitigation ho snižuje |

## Hit Chance
Základ **60 %**, každý bod **+2 %**, **20 bodů = jistý zásah**. Viz [staty](../stats/index.md#hit-chance).

## Krit
Základ **120 %** poškození, zvyšuje ho Crit Damage a talenty (až ~300 %).
Viz [staty](../stats/index.md#krit).

## Block
Jen [Warden](../classes/warrior/abilities.md#warden-tank-block-chance) (Warrior tank) a jen se štítem.
- Šance = 15 % + 1 % za bod Mastery (100 % při 85 Mastery).
- Úspěšný block sníží **fyzické** poškození o 40 %, při vyšší Mastery víc (nikdy ne 100 %).

## Mitigation
`redukce = M / (M + 100)`, platí na fyzické i magické poškození. Viz [staty](../stats/index.md#mitigation).

## Otevřené otázky
- Potvrdit pořadí kroků (hlavně block vs. mitigation vs. štíty).
- Počítá se poškození na serveru (PvP, cheaty)? Viz [síťování](../tech/networking.md).
