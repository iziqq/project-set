# Index wiki — Project Set

Katalog všech stránek wiki. Při každém ingestu se aktualizuje.
Formát: `- [Název](cesta.md) — jednořádkové shrnutí`

## Přehled
- [Overview](overview.md) — 2D RPG roguelike + PvP battle royale, 8 postav, volnost buildu

## Hra (game/)
- [Koncept](game/concept.md) — žánr, hráčská fantazie; kamera a core loop zatím chybí
- [Herní režimy](game/game-modes.md) — singleplayer roguelike, online co-op (max 5), PvP battle royale

## Mechaniky (mechanics/)
- [Postavy (classes)](mechanics/classes.md) — 8 postav, 19 speků (4 tank / 4 healer / 11 DPS), srovnávací tabulka base statů
- [Schopnosti](mechanics/abilities.md) — 5–6 aktivních na postavu + pasivky, šablona zápisu
- [Talenty](mechanics/talents.md) — strom, 20 talentů na postavu (obsah TBD)
- [Staty](mechanics/stats.md) — Primary (Str, Agi, Int, HP, Spirit), Secondary, vzorce Mitigation/CDR, hit 60 % + 2 %/bod, resource Mana/Rage/Energy
- [Štíty (absorb)](mechanics/shields.md) — srovnání štítů Paladina a Monka, pravidla skládání
- [Ekonomika](mechanics/economy.md) — Gold (budoucí měna)
- [Vybavení (equipment)](mechanics/equipment.md) — 13 slotů, HP + primary + secondary podle rarity, násobitele slotů, bez item levelu, reroll 60 %, sety 2/4/6/8

## Postavy (classes/)
- [Warrior](classes/warrior.md) — Rage, base staty (100 životů, Str 10, Agi 3), priorita Str/Agi, speky Warden (tank, Block) a Bleed Dancer (DPS, Bleed)
- [Paladin](classes/paladin.md) — Mana, 90 životů, speky Dawn Knight (tank, stun), Phoenix Rider (DPS, magický dmg), Light Bringer (healer, štít)
- [Scout](classes/scout.md) — Energy, 75 životů, Agi 12 / Str 6, priorita Agi/Str, Hawkeye (+0,3 % ranged dmg/bod), Adventurer (+0,5 % efektivita Agility/bod)
- [Wizard](classes/wizard.md) — Mana, 70 životů, Int 15 / Spirit 4, priorita jen Int, Pyromancer (Ignite DoT, řetězový přeskok na cíle bez Ignite) a Soultaker (+1 % + 0,1 %/bod dmg za nepřítele)
- [Summoner](classes/summoner.md) — speky Hell Knight (tank přes démona), Necromancer (kostlivec), Warlock (krátkodobí démoni), Mana, priorita Int
- [Monk](classes/monk.md) — Energy, speky Iron Turtle (tank, štít z dmg) a Deadly Tiger (DPS, bonus za cenu schopnosti), priorita Str/Agi
- [Shaman](classes/shaman.md) — Mana, Witch Doctor (heal z poškození) a Voodoo Master (Voodoo Doll), priorita Int
- [Cleric](classes/cleric.md) — speky Mind Bender (Insane), Prophet (buffer, Spirit 11), Bishop (Echo heal), Mana, priorita Int

## Technika (tech/)
- [Tech stack](tech/stack.md) — Godot 4 + C#/.NET, struktura projektu
- [Síťování](tech/networking.md) — online multiplayer, malý vlastní server (architektura TBD)

## Rozhodnutí (decisions/)
- [0001 — Godot + C#](decisions/0001-godot-csharp.md) — volba enginu a jazyka
- [0002 — Bez item levelu](decisions/0002-bez-item-levelu.md) — statické hodnoty statů, aby hra nebyla grind
- [0003 — Spec při výběru postavy](decisions/0003-spec-pri-vyberu-postavy.md) — spec určuje roli, base staty a Mastery
- [0004 — Resource typy](decisions/0004-resource-typy.md) — jen Mana / Rage / Energy, vlastní doplňování

## Zdroje (raw/)
- [2026-09-22 základní popis hry](../raw/2026-09-22-zakladni-popis-hry.md) — první popis od uživatele
- [2026-09-22 žánr, režimy, role](../raw/2026-09-22-zanr-rezimy-role.md) — žánr, multiplayer, talenty, equip, role postav
- [2026-09-22 staty](../raw/2026-09-22-staty.md) — primary/secondary staty a jejich hodnoty
- [2026-09-22 staty – upřesnění](../raw/2026-09-22-staty-upresneni.md) — vzorce, hit cap, range, resource
- [2026-09-22 hit & CDR](../raw/2026-09-22-hit-cdr.md) — hit 60 % + 2 %/bod, K = 50 pro CDR
- [2026-09-22 equipment](../raw/2026-09-22-equipment.md) — rarita, násobitele slotů, reroll, sety
- [2026-09-22 warrior](../raw/2026-09-22-warrior.md) — base staty, Mastery, Block Chance
- [2026-09-22 paladin](../raw/2026-09-22-paladin.md) — base staty podle role, Mastery
- [2026-09-22 scout](../raw/2026-09-22-scout.md) — 2 DPS varianty, base staty, Adventurer Mastery
- [2026-09-22 wizard](../raw/2026-09-22-wizard.md) — Spirit, Pyromancer, Soultaker
- [2026-09-22 summoner](../raw/2026-09-22-summoner.md) — 3 speky, base staty, Mastery
- [2026-09-23 monk](../raw/2026-09-23-monk.md) — base staty, Mastery tank/DPS
- [2026-09-23 shaman](../raw/2026-09-23-shaman.md) — speky, base staty, Mastery
- [2026-09-23 cleric](../raw/2026-09-23-cleric.md) — 3 speky, base staty, Mastery
- [2026-09-23 štíty](../raw/2026-09-23-stity.md) — sčítání štítů z různých zdrojů
- [2026-09-23 resource cleanup](../raw/2026-09-23-resource-cleanup.md) — vyřazení Hope a Darkness
- [2026-09-23 regenerace a názvosloví](../raw/2026-09-23-regenerace-role.md) — Rage/Energy regen, role vs. spec
- [2026-09-23 názvy speků](../raw/2026-09-23-nazvy-speku.md) — Warden, Bleed Dancer, Dawn Knight, Phoenix Rider, Light Bringer, Iron Turtle, Deadly Tiger

## Log
- [Log](log.md) — chronologický záznam změn wiki
