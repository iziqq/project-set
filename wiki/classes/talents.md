# Talenty

> Zdroje: [raw/2026-09-22-zakladni-popis-hry](../../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md) · Související: [classes](../classes/index.md), [staty](../stats/index.md)

- Každá [postava](../classes/index.md) má **20 talentů** (počet zatím předběžný).
- Talenty jsou uspořádané ve **stromu**.
- Talenty zlepšují postavu **určitým stylem**, tj. podporují konkrétní herní styl nebo build.
- Typy efektů:
  - vylepšení konkrétní **schopnosti**,
  - zvýšení **statů** ([staty](../stats/index.md)),
  - **změna škálování** — talent může převést stat na jiný účinek
    (např. Prophet: Intelligence se počítá do poškození ze zbraně,
    viz [Cleric](cleric/talents.md#prophet--autoattack-build)),
  - _další podle návrhu._
- Talenty smí **měnit roli postavy v sólo hře**, aniž by zesilovaly její skupinovou hodnotu —
  tak se řeší speky, které jsou záměrně slabé samy o sobě.
- Konkrétní talenty se navrhnou později.

## Kde jsou konkrétní stromy
V `wiki/classes/<postava>/talents.md`:
[Warrior](../classes/warrior/talents.md) · [Paladin](../classes/paladin/talents.md) ·
[Scout](../classes/scout/talents.md) · [Wizard](../classes/wizard/talents.md) ·
[Summoner](../classes/summoner/talents.md) · [Monk](../classes/monk/talents.md) ·
[Shaman](../classes/shaman/talents.md) · [Cleric](../classes/cleric/talents.md)

## Otevřené otázky
- Tvar stromu: jeden strom, nebo větve podle rolí (DPS / tank / healer)?
- Jak se talenty odemykají (level, body talentů)? Lze mít všech 20 najednou?
- Mají talenty více úrovní (ranků)?
- Roguelike: resetuje se strom s každým během, nebo je součástí meta-progrese?
- Respec?
