# Scout — schopnosti

> Související: [Scout](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Čísla jsou první nástřel k ladění.
> Poškození = % z **fyzického poškození** (roste z Agility a Strength). Resource: **Energy** (max. 100),
> doplňuje se **+5 za 3 s** (bez Spiritu) — schopnosti jsou proto levné a Scout má dva zdroje Energy navíc.

### Hawkeye (ranged) — 6 schopností
Střílí z **luku** (jediný spec, který ho může nosit). Mastery: +0,3 % poškození ranged zbraní za bod.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Aimed Shot** | 20 Energy | 6 s | 1 nepřítel | 200 % poškození, sesílání 1 s (nejde autoattackovat, viz [souboj](../../combat/index.md#autoattack)). |
| 2 | **Piercing Arrow** | 25 Energy | 12 s | linie | Šíp proletí nepřáteli v přímce: 130 % každému. |
| 3 | **Hunter's Mark** | 10 Energy | 20 s | 1 nepřítel | Označený cíl dostává **+20 % poškození od Hawkeye** po dobu 12 s. |
| 4 | **Rain of Arrows** | 30 Energy | 25 s | plocha | 5 vln po 50 % poškození na vybrané místo. |
| 5 | **Disengage** | 15 Energy | 15 s | sám | Odskok dozadu a **+30 % rychlosti pohybu** na 2 s. Udržuje odstup. |
| 6 | **Second Wind** | 0 Energy | 30 s | sám | Okamžitě **+40 Energy** a 5 s **+30 % Attack Speed**. |

Poznámky k návrhu:
- **Hunter's Mark** odměňuje soustředění na jeden cíl (boss), **Piercing Arrow** a **Rain of Arrows** skupiny.
- **Disengage** je jediná mobilita — Hawkeye má 75 životů, nejmíň z melee postav.
- **Second Wind** je záplata na pomalou regeneraci Energy.

### Adventurer (melee) — 6 schopností
Mastery: +0,5 % efektivity Agility za bod, takže Adventurer staví hlavně Agility.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Twin Strike** | 15 Energy | 4 s | 1 nepřítel | Dva seky po 90 % (každý může kritnout zvlášť). |
| 2 | **Shadowstep** | 15 Energy | 14 s | 1 nepřítel | Přemístí se za cíl; následující útok má **+50 % Crit Chance**. |
| 3 | **Whirl** | 25 Energy | 12 s | okolí (AoE) | 110 % poškození všem nepřátelům kolem. |
| 4 | **Exposing Cut** | 20 Energy | 15 s | 1 nepřítel | Cíl má **−25 % Mitigation** po dobu 8 s. |
| 5 | **Adrenaline** | 0 Energy | 30 s | sám | 8 s **+25 % Attack Speed** a okamžitě **+20 Energy**. |
| 6 | **Evasion** | 20 Energy | 40 s | sám | 4 s mají útočníci **−40 % Hit Chance** proti Adventurerovi. |

Poznámky k návrhu:
- **Shadowstep + Twin Strike** je jádro burstu: přemístění, zaručený krit, dva seky.
- **Exposing Cut** je podpora pro celou skupinu, protože Mitigation snižuje všem útočníkům.
- **Evasion** je jediná obrana Adventurera; staví na existující [Hit Chance](../../stats/index.md#hit-chance),
  takže nepotřebuje nový stat.

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Hawkeye (ranged): Poškození ranged zbraní
- Každý bod Mastery zvýší poškození s **ranged zbraní** o **0,3 %**.

| Mastery | Bonus |
|---|---|
| 50 | +15 % |
| 100 | +30 % |
| 200 | +60 % |

### Adventurer (melee): Efektivita Agility
- Každý bod Mastery zvyšuje **efektivitu Agility**. **200 Mastery = +100 %** (Agility dává dvojnásobek).
- Lineárně **+0,5 % za bod**, bez stropu.

```
agilityEffectivity = 1 + 0,005 × Mastery
```
| Mastery | Efektivita | 1 bod Agility dá |
|---|---|---|
| 0 | 100 % | +1 fyz. dmg, +1 Attack Speed, +1 Crit Chance |
| 100 | 150 % | +1,5 / +1,5 / +1,5 |
| 200 | 200 % | +2 / +2 / +2 |

### Další pasivky
_Doplnit._

## Rizika návrhu
- **Energy ekonomika:** +5 za 3 s je málo, Scout si vystačí jen díky levným schopnostem a
  Second Windu / Adrenalinu. Pokud se ukáže jako moc těsné, upravit regeneraci nebo ceny.
- **Evasion** zavádí snižování Hit Chance útočníkům — zatím se ve hře nikde jinde nesnižuje (?).
- **Rain of Arrows** cílí na místo, takže potřebuje zaměřování plochou — jediná taková schopnost zatím
  kromě [Phoenix Dive](../paladin/abilities.md).
