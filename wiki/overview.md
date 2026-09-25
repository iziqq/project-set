# Project Set — přehled

> Zdroje: [raw/2026-09-22-zakladni-popis-hry](../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-zanr-rezimy-role](../raw/2026-09-22-zanr-rezimy-role.md) · Poslední aktualizace: 2026-09-23

## Co je Project Set
2D **RPG roguelike** se třemi režimy: **singleplayer roguelike**, **online co-op roguelike**
(max. 5 hráčů) a **PvP RPG battle royale**. Hráč hraje za jednu z 8 postav, každá má vlastní
schopnosti, strom talentů a staty. Buildy jsou volné: postava se skládá přes talenty, vybavení
a přetváření statů na itemech.

## Hlavní systémy
- [Herní režimy](game/game-modes.md) — singleplayer, co-op, PvP battle royale
- [Postavy (classes)](classes/index.md) — 8 postav, všechny umí DPS, některé i tank / healer
- [Schopnosti](classes/abilities.md) — 5–6 aktivních na postavu + pasivky
- [Talenty](classes/talents.md) — strom, 20 talentů na postavu
- [Staty](stats/index.md) — primary / secondary staty, vzorce, resource (Mana / Rage / Energy)
- [Štíty](combat/shields.md) — absorb z healu (Paladin) a z poškození (Monk)
- [Vybavení (equipment)](equipment/index.md) — 13 slotů, 4 rarity, pevné staty, reroll za gold
- [Ekonomika](economy/index.md) — Gold
- [Síťování](tech/networking.md) — online, malý vlastní server

## Pilíře hry
1. **Volnost buildu** — hráč si postavu skládá podle svého stylu (talenty, equip, reroll statů).
2. **Znovuhratelnost** — roguelike běhy v singleplayeru i co-opu.
3. **Hraní s ostatními** — co-op pro 5 hráčů s rolemi tank / healer / DPS a PvP battle royale.

## Aktuální stav
- Repozitář, wiki a konvence založeny ([tech/stack](tech/stack.md)).
- **Hotovo:** žánr a režimy, staty a vzorce, equipment (rarita, sloty, reroll, sety),
  všech **8 postav** — base staty, speky, role, resource a Mastery ([classes](classes/index.md)).
- **Chybí:** schopnosti postav, obsah talentů, konkrétní itemy a jejich základní hodnoty,
  ekonomika (ceny), soubojový systém (aggro), síťová architektura, příběh a core loop.

## Otevřené otázky
- Perspektiva kamery (top-down / side-view)?
- Co přetrvává mezi roguelike běhy (meta-progrese)?
- Cílové platformy?
- Aggro / threat systém pro tanky ([classes](classes/index.md)).
