# 0004 — Resource jen Mana, Rage a Energy

- **Datum:** 2026-09-23
- **Stav:** přijato

## Kontext
Původní enum měl 5 typů: Mana Points, Rage, Hope, Darkness, Energy. Po návrhu všech 8 postav
používaly jen Manu (5 postav), Rage (Warrior) a Energy (Scout, Monk). Hope a Darkness zůstaly prázdné.

## Rozhodnutí
Enum se zkracuje na **Mana Points, Rage, Energy**. Hope a Darkness se vyřazují.
Každý typ má vlastní způsob doplňování ([staty](../mechanics/stats.md#resource-enum)):

| Resource | Doplňování |
|---|---|
| Mana | Spirit (% z max. / s) + Resource Regen z itemů |
| Rage | +10 za autoattack |
| Energy | +5 za 3 s |

## Důsledky
- Méně kódu i UI: tři typy zásobníků místo pěti.
- Postavy na Strength / Agility mají **Spirit 0** — je to záměr, ne chyba v base statech.
- Pět postav sdílí Manu, takže odlišnost musí nést Mastery a schopnosti, ne typ zdroje.
- Kdyby později vznikla postava, která si žádá vlastní zdroj, enum se dá rozšířit zpět.
