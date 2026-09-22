# Postavy (classes)

> Zdroje: [raw/2026-09-22-summoner](../../raw/2026-09-22-summoner.md), [raw/2026-09-22-wizard](../../raw/2026-09-22-wizard.md), [raw/2026-09-22-scout](../../raw/2026-09-22-scout.md), [raw/2026-09-22-paladin](../../raw/2026-09-22-paladin.md), [raw/2026-09-22-warrior](../../raw/2026-09-22-warrior.md), [raw/2026-09-22-zakladni-popis-hry](../../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md) · Související: [talenty](talents.md), [staty](stats.md), [equipment](equipment.md), [herní režimy](../game/game-modes.md)

Hráč hraje za postavu se specifickými schopnostmi. Každá postava má vlastní
[strom talentů](talents.md) (20 talentů) a specifické hodnoty [statů](stats.md).

## Stránky postav
Detail každé postavy je v `wiki/classes/<postava>.md`: base staty, povolené primary staty, Mastery a schopnosti.

| Class | Povolené primary (priorita) | Stav |
|---|---|---|
| [Warrior](../classes/warrior.md) | Strength, Agility | base staty, Mastery, resource; chybí schopnosti |
| [Paladin](../classes/paladin.md) | Strength, Agility, Intelligence | base staty podle role, Mastery, resource; chybí schopnosti |
| [Scout](../classes/scout.md) | Agility, Strength | 2 DPS varianty, base staty, Mastery, resource; chybí schopnosti |
| [Wizard](../classes/wizard.md) | Intelligence | 2 DPS varianty, base staty, Mastery (upřesnit), resource; chybí schopnosti |
| [Summoner](../classes/summoner.md) | Intelligence | 3 speky, base staty, Mastery, resource; chybí schopnosti |
| Monk, Shaman, Cleric | _Doplnit._ | nezačato |

## Role
**Všechny postavy umí DPS.** Některé mají navíc možnost hrát tanka nebo healera.
Roli (případně variantu v rámci role, např. Scout ranged / melee) si hráč **volí při výběru postavy**. Role může měnit base staty a Mastery (viz [Paladin](../classes/paladin.md)).

| Class | DPS | Tank | Healer | Poznámka | Resource (?) |
|---|:-:|:-:|:-:|---|---|
| [Warrior](../classes/warrior.md) | ✔ | ✔ | | tank jen s **weapon + shield**, Mastery: tank = Block Chance, DPS = Bleed | **Rage** |
| [Paladin](../classes/paladin.md) | ✔ | ✔ | ✔ | jediná postava se všemi třemi rolemi | **Mana** |
| [Scout](../classes/scout.md) | ✔ | | | 2 DPS varianty: Hawkeye (ranged), Adventurer (melee) | **Energy** |
| [Wizard](../classes/wizard.md) | ✔ | | | 2 DPS varianty: Pyromancer, Soultaker | **Mana** |
| [Summoner](../classes/summoner.md) | ✔ | ✔ | | speky: Hell Knight (tank přes démona), Necromancer, Warlock | **Mana** |
| Monk | ✔ | ✔ | | | Energy (?) |
| Shaman | ✔ | | ✔ | | Mana Points (?) |
| Cleric | ✔ | | ✔ | | Hope / Mana (?) |

Vybavení nemá žádná omezení podle postavy ([equipment](equipment.md)). Postava ale omezuje, jakou
**prioritu primary statu** pro dropy si hráč může zvolit (např. Wizard ne Strength).

Přehled: tank = Warrior, Paladin, Monk, Summoner · healer = Paladin, Cleric, Shaman · jen DPS = Scout, Wizard.

Resource u postav je stále jen **odhad**, uživatel ho zatím nepotvrdil.

## Otevřené otázky
- **Aggro / threat:** jak nepřátelé volí cíl? Tank (a démon Hell Knighta) potřebuje mechaniku, jak na sebe strhnout pozornost (taunt, threat podle poškození…).
- Lze roli po výběru postavy změnit (mezi běhy, respec)?
- Kolik aktivních schopností má postava? Ovládání (hotbar, cooldowny)?
- Resource pro každou postavu.
- Které primary staty (Str / Agi / Int) si může každá postava zvolit jako prioritu?
