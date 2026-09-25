# 0002 — Žádný item level, statické hodnoty statů

- **Datum:** 2026-09-22
- **Stav:** přijato

## Kontext
Hry s item levelem nutí hráče opakovaně sbírat lepší verze téhož předmětu. Uživatel to nechce:
„Nechci z toho mít permanentní grind.“

## Rozhodnutí
Itemy nemají level. Hodnoty statů jsou **statické** a vycházejí ze vzorce
`základní hodnota × násobitel rarity × násobitel slotu` ([equipment](../equipment/index.md)).

## Důsledky
- Postup hráče jde přes **rarity, buildy a přetváření statů**, ne přes rostoucí čísla.
- Endgame nemůže stát na „lepších dropech“ — musí stát na obtížnosti, setech a talentech.
- Balanc je snazší: možné hodnoty statů jsou konečná, spočitatelná množina.
- Silná Legendary výbava je cíl, ne mezikrok.
