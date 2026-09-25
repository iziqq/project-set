# Aggro / threat

> Zdroje: [raw/2026-09-25-threat-aoe](../../raw/2026-09-25-threat-aoe.md) · Související: [souboj](index.md), [postavy](../classes/index.md), [schopnosti](../classes/abilities.md)

## Pravidla
- Každá postava má u každého nepřítele **threat**.
- Nepřítel útočí na toho, kdo má u něj **nejvyšší threat** (má „aggro“).
- Threat se generuje z **poškození** a **healu**.
- **Tank speky mají 10× vyšší generaci threatu** než ostatní speky.
- **Heal generuje threat u všech nepřátel v boji**, ne jen u těch, kteří útočí na léčeného.
- **Threat klesá o 10 % za sekundu**, ale jen tomu, kdo **3 s negeneroval** žádný threat.
- **Démon Hell Knighta má vlastní threat** — threat za jeho poškození se počítá démonovi, ne Summonerovi
  (a platí pro něj 10× bonus tank speku (?)).

```
threat += (poškození nebo heal) × (tank spec ? 10 : 1)
lastThreatAt = now

každou sekundu, pro každého:
    if now - lastThreatAt >= 3s:  threat × 0,9
```
Kdo bojuje, o threat nepřichází. Kdo přestane (DPS, který si vytáhl aggro, nebo healer, který nemá
co léčit), začne po 3 s ztrácet 10 % za sekundu a tank ho dožene.

## Taunt
- Taunt **ignoruje threat**: nepřítel útočí **2 s** vždy na tanka.
- Zároveň **vynuluje threat všem hráčům** u tohoto nepřítele — threat se počítá znovu **od 0**.
- Po 2 s rozhoduje zase threat. Tank má díky 10× generaci náskok, protože všichni začínají od nuly.

```
onTaunt(enemy, tank):
    enemy.threatTable.clear()      // všichni na 0
    enemy.forcedTarget = tank
    enemy.forcedUntil = now + 2s
```

## Důsledky
- Tank nemusí dávat největší poškození, stačí mu desetinové, aby udržel aggro.
- Healer generuje threat na **všechny** nepřátele v boji, takže bez tanka rychle chytne aggro celé skupiny.
- DPS má prostor zhruba do desetinásobku tankova poškození, než mu aggro sebere.

## Tanci a AoE
**Každý tank spec musí mít AoE schopnost**, aby udržel aggro na skupině nepřátel
(pravidlo pro návrh schopností, viz [schopnosti](../classes/abilities.md)).

Tank speky: [Warden](../classes/warrior/abilities.md), [Dawn Knight](../classes/paladin/abilities.md),
[Hell Knight](../classes/summoner/abilities.md), [Iron Turtle](../classes/monk/abilities.md).

## Otevřené otázky
- Generuje heal threat u všech nepřátel v boji, nebo jen u těch, co útočí na léčeného?
- Threat **démona Hell Knighta**: má démon vlastní threat s 10× bonusem, nebo se počítá Summonerovi?
- Resetuje se threat po smrti hráče a po konci boje?
- Mají nepřátelé „preferované cíle“ (boss mechaniky ignorující threat)?
