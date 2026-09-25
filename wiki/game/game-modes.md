# Herní režimy

> Zdroje: [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md) · Související: [koncept](concept.md), [síťování](../tech/networking.md), [classes](../classes/index.md)

| Režim | Typ | Hráči | Síť |
|---|---|---|---|
| Singleplayer | RPG roguelike | 1 | offline (?) |
| Co-op | RPG roguelike | 2–5 | online |
| PvP | RPG battle royale | _Doplnit._ | online |

## Singleplayer roguelike
Solo běhy. _Detaily doplnit._

## Co-op roguelike
- Max. **5 hráčů**, online.
- V co-opu mají smysl role tank / healer / DPS ([classes](../classes/index.md)).

## PvP battle royale
- RPG battle royale: hráči proti sobě, poslední přeživší vyhrává (?).
- **PvP může mít vlastní koeficienty balancu** (např. vyšší Mastery koeficient pro [Soultakera](../classes/wizard/index.md#soultaker-poškození-podle-počtu-nepřátel)). Implementačně: balanční data ve variantách PvE / PvP.
- _Detaily doplnit._

## Otevřené otázky
- Počet hráčů v battle royale? Solo, nebo týmy?
- Jak funguje battle royale ve 2D: zmenšující se mapa, loot na mapě, začínají hráči s „nulou“?
- Nese si hráč do PvP postavu a equip z roguelike, nebo PvP startuje od nuly?
- Škálování obtížnosti co-opu podle počtu hráčů?
- Loot v co-opu: sdílený, nebo osobní?
- Funguje singleplayer offline?
