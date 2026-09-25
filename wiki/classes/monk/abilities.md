# Monk — schopnosti

> Související: [Monk](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Poškození = % z **fyzického poškození**.
> Resource: **Energy** (max. 100), doplňuje se **+5 za 3 s** — schopnosti jsou levné.

### Iron Turtle (tank) — 6 schopností
Ze způsobeného poškození si dělá [štít](#iron-turtle-tank-štít-z-poškození), takže musí útočit.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Palm Strike** | 15 Energy | 4 s | 1 nepřítel | 120 % poškození. Základ pro štít i threat. |
| 2 | **Sweeping Kick** | 20 Energy | 10 s | okolí (AoE) | 90 % poškození všem kolem — AoE threat a štít ze všech zásahů. |
| 3 | **Challenging Shout** | 10 Energy | 12 s | okolí | **Taunt** 2 s, vynuluje threat ([threat](../../combat/threat.md)). |
| 4 | **Turtle Stance** | 25 Energy | 30 s | sám | 6 s **+80 % Mitigation**, ale **−50 % rychlosti pohybu**. |
| 5 | **Chi Barrier** | 20 Energy | 25 s | sám | Spotřebuje aktuální štít a vyléčí **150 % jeho hodnoty**. |
| 6 | **Stone Skin** | 0 Energy | 60 s | sám | 8 s se štít z Mastery počítá **dvojnásobně**. |

Poznámky: **Chi Barrier** mění dočasný štít (6 s) na trvalé životy — odměna za včasné použití.
**Sweeping Kick** plní pravidlo AoE pro tanky.

### Deadly Tiger (DPS) — 6 schopností
Mastery zvyšuje poškození podle **ceny schopnosti v Energy**, takže drahé schopnosti jsou jeho jádro.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Tiger Claw** | 25 Energy | 5 s | 1 nepřítel | 180 % poškození. |
| 2 | **Roaring Fist** | 40 Energy | 12 s | 1 nepřítel | 260 % poškození. Nejdražší útok = největší bonus z Mastery. |
| 3 | **Flurry** | 20 Energy | 8 s | 1 nepřítel | 4 údery po 60 %, každý může kritnout. |
| 4 | **Leaping Strike** | 15 Energy | 14 s | 1 nepřítel | Skok na cíl, 120 % poškození. Mobilita. |
| 5 | **Inner Fire** | 0 Energy | 30 s | sám | 8 s stojí schopnosti **+50 % Energy**, ale dávají **+50 % poškození** (i větší bonus z Mastery). |
| 6 | **Meditate** | 0 Energy | 25 s | sám | Sesílá 3 s: **+60 Energy**. Během toho nemůže útočit. |

Poznámky: **Inner Fire** je hazard — vyšší cena znamená větší Mastery bonus, ale rychleji dojde Energy.
**Meditate** je protiváha: pauza v boji výměnou za zásobu.

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Iron Turtle (tank): Štít z poškození
- **10 % poškození, které Iron Turtle způsobí**, se změní na **štít** (absorb) na Monkovi, trvání **6 s**.
- Každý bod Mastery přidá **+0,5 %**.

```
shield% = 10 % + 0,5 % × Mastery
```
| Mastery | Podíl na štít |
|---|---|
| 0 | 10 % |
| 10 | 15 % |
| 50 | 35 % |
| 100 | 60 % |

**Chování štítu** (jiné než [Paladinův štít](../paladin/abilities.md#light-bringer-healer-štít-z-healu), viz [štíty](../../combat/shields.md)):
- **Nesčítá se.**
- Nový štít **větší** než současný → **přepíše** ho (a trvání začne znovu).
- Nový štít **menší** → jen **obnoví trvání** na 6 s.

### Deadly Tiger (DPS): Poškození za energy
- Každý bod Mastery zvýší poškození schopnosti o **0,1 % za každý bod energy**, který schopnost stojí.
- Příklad: 10 Mastery = 1 % za energy → schopnost za 30 energy má **+30 %** poškození.

```
dmgBonus = 0,1 % × Mastery × cenaSchopnosti(energy)
```
| Mastery | Schopnost za 10 | za 30 | za 50 |
|---|---|---|---|
| 10 | +10 % | +30 % | +50 % |
| 50 | +50 % | +150 % | +250 % |
| 100 | +100 % | +300 % | +500 % |

Záměr: odměňuje drahé schopnosti, nevýhodou je jejich cena a nutnost regenerace.
Škálování je strmé (100 Mastery, schopnost za 50 → +500 %). Uživatel to bude ladit později.

### Další pasivky
_Doplnit._

## Rizika návrhu
- **Inner Fire × Mastery** se násobí dvakrát (dražší schopnost i +50 % poškození) — hlídat při ladění.
- **Chi Barrier** potřebuje jasné pravidlo, co se stane, když je štít 0 (návrh: schopnost nejde použít).
