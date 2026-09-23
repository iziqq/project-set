# 0003 — Spec se volí při výběru postavy

- **Datum:** 2026-09-22
- **Stav:** přijato

## Kontext
Postavy mají různé base staty a jiné Mastery podle role (Paladin tank 15 Str, healer 15 Int).
Warriorovu roli původně určoval jen štít. Bylo potřeba určit, kdy a jak se role volí.

## Rozhodnutí
Hráč volí **spec při výběru postavy**. Spec určuje roli (Tank / DPS / Healer), base staty a Mastery.
Vybavení může spec doplňovat (Warrior tank potřebuje štít), ale nevolí ho.

## Důsledky
- Base staty a Mastery lze definovat per spec, ne per class.
- Hráč se rozhoduje dřív, než najde vybavení — spec musí být čitelný už z popisu.
- Nutné rozhodnout, zda a kdy jde spec změnit (otevřená otázka v [classes](../mechanics/classes.md)).
- V co-opu se role domlouvají před během, ne během něj.
