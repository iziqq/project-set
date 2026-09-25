# Souboj (combat)

> Související: [staty](../stats/index.md), [schopnosti](../classes/abilities.md), [postavy](../classes/index.md)

Obecná pravidla boje. Konkrétní efekty patří k postavám
(`classes/<postava>/abilities.md`), tady jsou **pravidla, která platí napříč**.

## Stránky
- [Výpočet poškození](damage.md) — pořadí: hit → crit → block → mitigation
- [Štíty (absorb)](shields.md) — Light Bringer, Iron Turtle, skládání vrstev
- [Efekty](effects.md) — buffy, debuffy, DoT, crowd control
- [Aggro / threat](threat.md) — kdo má aggro, tank generuje 10× threat

## Autoattack
- Základní útok bez ceny, opakuje se automaticky. Rychlost určuje **Attack Speed**, dosah **Range zbraně**.
- **Během sesílání kouzla postava nemůže autoattackovat.** Platí obecně: castování a autoattack
  se vylučují, takže se nedá „kouzlit a zároveň mlátit“.
- Autoattack krmí resource a pasivky: Warrior **+10 Rage**, Paladin **+5 % Many**
  ([Divine Spark](../classes/paladin/abilities.md#divine-spark--všechny-speky-paladina)).

## Zatím nevyřešené
- Smrt a respawn v roguelike běhu.
