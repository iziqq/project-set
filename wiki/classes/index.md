# Postavy (classes)

> Zdroje: [raw/2026-09-23-cleric](../../raw/2026-09-23-cleric.md), [raw/2026-09-23-shaman](../../raw/2026-09-23-shaman.md), [raw/2026-09-23-monk](../../raw/2026-09-23-monk.md), [raw/2026-09-22-summoner](../../raw/2026-09-22-summoner.md), [raw/2026-09-22-wizard](../../raw/2026-09-22-wizard.md), [raw/2026-09-22-scout](../../raw/2026-09-22-scout.md), [raw/2026-09-22-paladin](../../raw/2026-09-22-paladin.md), [raw/2026-09-22-warrior](../../raw/2026-09-22-warrior.md), [raw/2026-09-22-zakladni-popis-hry](../../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md) · Zdroje též: [raw/2026-09-23-nazvy-speku](../../raw/2026-09-23-nazvy-speku.md) · Související: [schopnosti](abilities.md), [talenty](talents.md), [staty](../stats/index.md), [equipment](../equipment/index.md), [štíty](../combat/shields.md), [herní režimy](../game/game-modes.md)

Hráč hraje za postavu se specifickými schopnostmi. Každá postava má vlastní
[strom talentů](talents.md) (20 talentů) a specifické hodnoty [statů](../stats/index.md).

## Stránky postav
Detail každé postavy je ve složce `wiki/classes/<postava>/`: `index.md` (base staty, povolené primary
staty, role a speky, Mastery), `abilities.md` (schopnosti), `talents.md` (strom talentů).

| Class | Povolené primary (priorita) | Stav |
|---|---|---|
| [Warrior](../classes/warrior/index.md) | Strength, Agility | base staty, Mastery, resource; chybí schopnosti |
| [Paladin](../classes/paladin/index.md) | Strength, Agility, Intelligence | base staty podle role, Mastery, resource; chybí schopnosti |
| [Scout](../classes/scout/index.md) | Agility, Strength | 2 DPS varianty, base staty, Mastery, resource; chybí schopnosti |
| [Wizard](../classes/wizard/index.md) | Intelligence | 2 DPS varianty, base staty, Mastery, resource; chybí schopnosti |
| [Summoner](../classes/summoner/index.md) | Intelligence | 3 speky, base staty, Mastery, resource; chybí schopnosti |
| [Monk](../classes/monk/index.md) | Strength, Agility | tank + DPS, base staty, Mastery, resource; chybí schopnosti |
| [Shaman](../classes/shaman/index.md) | Intelligence | heal + DPS spek, base staty, Mastery, resource; chybí schopnosti |
| [Cleric](../classes/cleric/index.md) | Intelligence | 3 speky, base staty, Mastery, resource; chybí schopnosti a buffy Propheta |

## Názvosloví: role a spec
- **Role** = **Tank**, **DPS**, **Healer**.
- **Spec** = konkrétní specializace se jménem (např. Hawkeye, Prophet). Každý spec má jednu roli,
  vlastní base staty a vlastní Mastery.
- Hráč volí **spec při výběru postavy** ([ADR 0003](../decisions/0003-spec-pri-vyberu-postavy.md)).

**Všechny postavy mají aspoň jeden DPS spec.** Některé mají i tank nebo healer spec.

| Class | DPS | Tank | Healer | Speky | Resource |
|---|:-:|:-:|:-:|---|---|
| [Warrior](../classes/warrior/index.md) | ✔ | ✔ | | Warden (tank, weapon + shield, Block Chance), Bleed Dancer (DPS, Bleed) | **Rage** |
| [Paladin](../classes/paladin/index.md) | ✔ | ✔ | ✔ | Dawn Knight (tank), Phoenix Rider (DPS), Light Bringer (healer) | **Mana** |
| [Scout](../classes/scout/index.md) | ✔ | | | Hawkeye (ranged), Adventurer (melee) | **Energy** |
| [Wizard](../classes/wizard/index.md) | ✔ | | | Pyromancer, Soultaker | **Mana** |
| [Summoner](../classes/summoner/index.md) | ✔ | ✔ | | Hell Knight (tank přes démona), Necromancer, Warlock | **Mana** |
| [Monk](../classes/monk/index.md) | ✔ | ✔ | | Iron Turtle (tank, štít z poškození), Deadly Tiger (DPS, bonus za cenu schopnosti) | **Energy** |
| [Shaman](../classes/shaman/index.md) | ✔ | | ✔ | Witch Doctor (healer), Voodoo Master (DPS) | **Mana** |
| [Cleric](../classes/cleric/index.md) | ✔ | | ✔ | Mind Bender (DPS), Prophet (buffer), Bishop (healer) | **Mana** |

Vybavení nemá žádná omezení podle postavy ([equipment](../equipment/index.md)). Postava ale omezuje, jakou
**prioritu primary statu** pro dropy si hráč může zvolit (např. Wizard ne Strength).

Přehled: tank = Warrior, Paladin, Monk, Summoner · healer = Paladin, Cleric, Shaman · jen DPS = Scout, Wizard.

## Počty speků podle rolí
**8 postav, 19 speků.**

| Role | Počet | Speky |
|---|---|---|
| **Tank** | 4 | Warden (Warrior), Dawn Knight (Paladin), Hell Knight (Summoner), Iron Turtle (Monk) |
| **Healer** | 4 | Light Bringer (Paladin), Witch Doctor (Shaman), Prophet (Cleric), Bishop (Cleric) |
| **DPS** | 11 | Bleed Dancer (Warrior), Phoenix Rider (Paladin), Hawkeye + Adventurer (Scout), Pyromancer + Soultaker (Wizard), Necromancer + Warlock (Summoner), Deadly Tiger (Monk), Voodoo Master (Shaman), Mind Bender (Cleric) |

V co-opu pro 5 hráčů (1 tank + 1 healer + 3 DPS) poměr sedí.

## Base staty všech postav
Body HP × 5 = životy. Prázdné = 0.

| Class | Spec | Role | HP (body / životy) | Str | Agi | Int | Spirit |
|---|---|---|---|---|---|---|---|
| [Warrior](../classes/warrior/index.md) | Warden / Bleed Dancer | tank / DPS | 20 / 100 | 10 | 3 | | |
| [Paladin](../classes/paladin/index.md) | Dawn Knight | tank | 18 / 90 | 15 | | | |
| [Paladin](../classes/paladin/index.md) | Phoenix Rider | DPS | 18 / 90 | 11 | 4 | | |
| [Paladin](../classes/paladin/index.md) | Light Bringer | healer | 18 / 90 | | | 15 | |
| [Scout](../classes/scout/index.md) | Hawkeye, Adventurer | DPS | 15 / 75 | 6 | 12 | | |
| [Wizard](../classes/wizard/index.md) | Pyromancer, Soultaker | DPS | 14 / 70 | | | 15 | 4 |
| [Summoner](../classes/summoner/index.md) | Hell Knight | tank | 18 / 90 | | | 10 | 5 |
| [Summoner](../classes/summoner/index.md) | Necromancer, Warlock | DPS | 13 / 65 | | | 15 | 5 |
| [Monk](../classes/monk/index.md) | Iron Turtle | tank | 18 / 90 | 9 | 6 | | |
| [Monk](../classes/monk/index.md) | Deadly Tiger | DPS | 16 / 80 | 8 | 9 | | |
| [Shaman](../classes/shaman/index.md) | Witch Doctor | healer | 16 / 80 | | | 8 | 9 |
| [Shaman](../classes/shaman/index.md) | Voodoo Master | DPS | 16 / 80 | | | 10 | 7 |
| [Cleric](../classes/cleric/index.md) | Mind Bender | DPS | 16 / 80 | | | 10 | 7 |
| [Cleric](../classes/cleric/index.md) | Prophet | healer | 18 / 90 | | | 4 | 11 |
| [Cleric](../classes/cleric/index.md) | Bishop | healer | 16 / 80 | | | 8 | 9 |

Postavy na Strength / Agility mají **Spirit 0** záměrně — Rage a Energy se doplňují jinak
(Rage +10 za autoattack, Energy +5 za 3 s), viz [resource](../stats/index.md#resource-enum).

## Schopnosti
Každá postava má **5–6 aktivních schopností** a několik pasivek. Šablona a pravidla:
[schopnosti](abilities.md).

## Otevřené otázky
- **Aggro / threat:** řeší se v [souboji](../combat/index.md).
- Lze roli po výběru postavy změnit (mezi běhy, respec)?
- Kolik aktivních schopností má postava? Ovládání (hotbar, cooldowny)?
