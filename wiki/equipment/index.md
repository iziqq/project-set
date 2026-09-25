# Vybavení (equipment)

> Zdroje: [raw/2026-09-22-zakladni-popis-hry](../../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md), [raw/2026-09-22-equipment](../../raw/2026-09-22-equipment.md) · Související: [staty](../stats/index.md), [classes](../classes/index.md), [ekonomika](../economy/index.md)

Cíl: hra má být **dynamická**, každý hráč si vybavením skládá build podle sebe.

## Principy
- **Žádná omezení:** každá postava může nosit cokoli (Wizard se štítem, Warrior s holí…).
  **Výjimka: luk** může nosit jen [Scout Hawkeye](../classes/scout/index.md).
- **Žádný item level:** hodnoty statů jsou **statické**. Záměrně, aby hra nebyla nekonečný grind
  ([ADR 0002](../decisions/0002-bez-item-levelu.md)).
- Síla itemu = **základní hodnota × násobitel rarity × násobitel slotu**.

## Itemy podle slotů
Konkrétní itemy jsou ve složkách podle slotu:
[Heads](heads/index.md) · [Chests](chests/index.md) · [Legs](legs/index.md) ·
[Gloves](gloves/index.md) · [Belts](belts/index.md) · [Boots](boots/index.md) ·
[Rings](rings/index.md) · [Earrings](earrings/index.md) · [Weapons](weapons/index.md) ·
[Off-hands](offhands/index.md) · [Talismans](talismans/index.md)

## Sloty (13)
| # | Slot | Poznámka |
|---|---|---|
| 1 | Head | |
| 2 | Chest | |
| 3 | Gloves | |
| 4 | Belt | |
| 5 | Legs | |
| 6 | Boots | |
| 7 | Ring 1 | |
| 8 | Ring 2 | |
| 9 | Earring 1 | |
| 10 | Earring 2 | |
| 11 | Weapon | |
| 12 | Shield / Off-hand | **2H Weapon zabírá Weapon i Off-hand** |
| 13 | Talisman | |

## Range zbraní
- Dosah útoku určuje **zbraň**: **Range** je **statická hodnota** daná typem zbraně (luk daleko,
  melee zbraně blízko). Není to rollovaný stat a nejde přetvořit.

## Složení itemu
Každý item má:
1. **HP** (vždy),
2. **druhý primary stat** (Strength / Agility / Intelligence; **Spirit na itemech není**) podle **priority**, kterou si hráč
   nastaví u postavy. Dropy pak generují zvolený stat. Výběr priority je **omezen postavou**
   (např. Wizard nemůže zvolit Strength), viz [classes](../classes/index.md).
3. **secondary staty** podle rarity.

Výjimka: **Talisman** má **vždy přesně jeden secondary stat** (žádné HP ani primary), zato hodně silný.
Druhý stat může vzniknout jen přetvořením.

## Rarita
| Rarita | Primary staty | Secondary staty | Počet statů celkem |
|---|---|---|---|
| Common | 50 % | 1× 50 % | 3 |
| Rare | 70 % | 1× 70 % | 3 |
| Epic | 85 % | 2× 50 % | 4 |
| Legendary | 100 % | 3× 50 % | 5 |

Procenta jsou z **základní hodnoty** statu (100 %). Základní hodnoty se určí při návrhu konkrétních itemů.

## Násobitel slotu
| Slot | Primary | Secondary |
|---|---|---|
| Head, Chest, Legs | 100 % | 100 % |
| Gloves, Belt, Boots | 70 % | 70 % |
| Ring, Earring | 50 % | **150 %** |
| Talisman | — | vlastní škála podle rarity, viz níže (jen 1 stat) |
| Shield / Off-hand | 60 % | 60 % |
| Weapon (1H) | 100 % | 100 % |
| 2H Weapon | 150 % | 150 % |

### Výsledná matice (násobek základní hodnoty)
Primary staty (HP + druhý primary):

| Slot | Common | Rare | Epic | Legendary |
|---|---|---|---|---|
| Head / Chest / Legs / Weapon | 0,50 | 0,70 | 0,85 | 1,00 |
| Gloves / Belt / Boots | 0,35 | 0,49 | 0,60 | 0,70 |
| Ring / Earring | 0,25 | 0,35 | 0,43 | 0,50 |
| Shield / Off-hand | 0,30 | 0,42 | 0,51 | 0,60 |
| 2H Weapon | 0,75 | 1,05 | 1,28 | 1,50 |

Secondary staty (hodnota **jednoho** secondary statu):

| Slot | Common | Rare | Epic | Legendary |
|---|---|---|---|---|
| Head / Chest / Legs / Weapon | 0,50 | 0,70 | 0,50 | 0,50 |
| Gloves / Belt / Boots | 0,35 | 0,49 | 0,35 | 0,35 |
| Ring / Earring | 0,75 | 1,05 | 0,75 | 0,75 |
| Shield / Off-hand | 0,30 | 0,42 | 0,30 | 0,30 |
| 2H Weapon | 0,75 | 1,05 | 0,75 | 0,75 |
| Talisman | 1,50 | 2,00 | 2,50 | 3,00 |

Pozn.: Jeden secondary stat je u Rare silnější než u Epic a Legendary. Ty ale mají víc statů,
takže celkový součet secondary je 50 / 70 / 100 / 150 %.

### Talisman
Talisman má **vlastní škálu** a neřídí se tabulkou rarity ani násobitelem slotu:

| Rarita | Síla secondary statu |
|---|---|
| Common | 150 % |
| Rare | 200 % |
| Epic | 250 % |
| Legendary | 300 % |

## Přetvoření statu (reroll)
- Za [Gold](../economy/index.md) lze **60 % jednoho statu** převést na jiný stat podle volby hráče.
  Příklad: 100 Strength → 40 Strength + 60 Agility.
- **Primary → jen primary**, **secondary → jen secondary**.
- Na každém itemu **jen 1×**. Hráč může přetvoření **zrušit** a udělat jinak.
- Přetvořit jde i **HP** (je to primary stat). Hráč si může životy vyměnit za útok, ale riskuje rychlou smrt.
- U talismanu přetvoření rozdělí jediný secondary stat na dva.
- Cena v Goldu: řeší [ekonomika](../economy/index.md).

## Setové bonusy
- Budou, a to **více setů**.
- Bonusy za **2 / 4 / 6 / 8** kusů.
- Konkrétní sety se navrhnou až po vymyšlení itemů.

## Rozpory
- „Žádná omezení, ať si každý nosí co chce“ × luk jen pro Scout Hawkeye. Bráno jako záměrná výjimka.

## Poznámky z diskuze
- 2H Weapon (150 %) má **záměrně** o něco méně statů než Weapon + Off-hand (100 % + 60 % = 160 %).
  Vyrovná to o něco silnějšími útoky.

## Otevřené otázky
- **Typy zbraní:** jaké typy zbraní existují (luk, meč, hůl…)? Jsou kromě luku další ranged zbraně? Jaké Range mají jednotlivé typy?
- **Základní hodnoty (100 %)** pro HP, primary a secondary se určí při návrhu itemů.
- Odkud se itemy berou (drop, crafting, obchod)? Přetrvávají mezi roguelike běhy?
- Jsou staty v rámci jedné rarity a slotu vždy stejné, nebo se liší podle konkrétního itemu (unikátní itemy)?
