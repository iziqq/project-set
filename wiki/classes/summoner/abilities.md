# Summoner — schopnosti

> Související: [Summoner](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Stav: návrh (předběžně odsouhlasen 2026-09-25).** Čísla se budou ladit při testování.
> Poškození = % z **magického poškození** (roste z Intelligence). Resource: **Mana** (max. 100),
> regenerace přes **Spirit 5**.
> Summoner bojuje přes vyvolané bytosti — jejich parametry určují schopnosti, které je vyvolávají.

### Hell Knight (tank) — 6 schopností
Tankuje **démon**, ne Summoner. Threat se počítá démonovi ([threat](../../combat/threat.md)).

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Summon Infernal** | 40 Mana | 10 s | — | Vyvolá **permanentního démona** (parametry níže). Po jeho smrti se dá vyvolat znovu. |
| 2 | **Hellfire Roar** | 25 Mana | 15 s | okolí (AoE) | Démon zařve: 60 % poškození všem v okruhu a **taunt 2 s** — AoE i taunt pro tank spec. |
| 3 | **Infernal Mend** | 25 Mana | 8 s | démon | Vyléčí démona za **25 % jeho max. HP**. |
| 4 | **Soul Link** | 30 Mana | 30 s | démon | 10 s se **30 % poškození démona** přesměruje na Summonera. |
| 5 | **Dark Pact** | 10 % vlastních HP | 20 s | démon | Démon má 8 s **+50 % poškození** a generuje víc threatu. |
| 6 | **Abyssal Chains** | 20 Mana | 18 s | okolí | Znehybní nepřátele v okruhu na **2 s**. |

Poznámky k návrhu:
- **Hellfire Roar** plní obě povinnosti tank speku: AoE i taunt.
- **Soul Link** je cena za to, že Hell Knight je „méně efektivní tank“ — přežití démona si platí
  vlastními životy.
- **Dark Pact** stojí HP, ne Manu; Summoner má nejméně životů z tanků (90).

### Necromancer (DPS) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Raise Skeleton** | 40 Mana | 15 s | — | Vyvolá **permanentního kostlivce** (parametry níže). |
| 2 | **Bone Spear** | 15 Mana | 4 s | 1 nepřítel | 150 % magického poškození. |
| 3 | **Command: Rend** | 20 Mana | 10 s | 1 nepřítel | Kostlivec zaútočí za **200 % svého poškození**. |
| 4 | **Corpse Explosion** | 25 Mana | 12 s | mrtvola | Mrtvola nepřítele vybuchne: 180 % poškození v okruhu. |
| 5 | **Death Coil** | 25 Mana | 15 s | 1 nepřítel | 120 % poškození a stejnou hodnotu vyléčí kostlivci. |
| 6 | **Soul Harvest** | 30 Mana | 25 s | sám | Za každého nepřítele zabitého za posledních 10 s **+5 % poškození** (na 10 s). |

Poznámky k návrhu:
- Kostlivec je trvalý parťák, takže **Mastery** (+1 % jeho poškození za bod) je páteř speku.
- **Corpse Explosion** a **Soul Harvest** odměňují boj proti skupinám.

### Warlock (DPS) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Summon Imps** | 30 Mana | 12 s | — | 3 impové na **8 s** (+ [Mastery](#warlock-dps-trvání-démonů)). |
| 2 | **Summon Hellhound** | 35 Mana | 20 s | — | Rychlý pes na **10 s**, melee. |
| 3 | **Summon Void Terror** | 50 Mana | 45 s | — | Velký démon na **12 s**, vysoké poškození. |
| 4 | **Shadow Bolt** | 15 Mana | 3 s | 1 nepřítel | 130 % magického poškození. |
| 5 | **Sacrifice** | 0 Mana | 10 s | vlastní démon | Obětuje jednoho démona: exploze za **200 %** v okruhu. |
| 6 | **Demonic Surge** | 25 Mana | 30 s | vlastní démoni | Všichni aktivní démoni mají 6 s **+50 % poškození**. |

Poznámky k návrhu:
- Warlock žongluje s časem: Mastery prodlužuje trvání, **Sacrifice** mění zbytek života démona na poškození.
- Vyvolávání stojí hodně Many — Spirit 5 a Resource Regen z itemů určují tempo.

## Vyvolané bytosti
Parametry určuje schopnost, která bytost vyvolá. **Každá bytost má i vlastní schopnosti** — používá
je **sama (AI)** na vlastní cooldown, Summoner je nemusí ovládat a nemá je na hotbaru.

| Bytost | Spec | Trvání | HP | Poškození |
|---|---|---|---|---|
| **Infernal** | Hell Knight | permanentní | _Doplnit._ + [Mastery](#hell-knight-obrana-démona) | _Doplnit._ |
| **Kostlivec** | Necromancer | permanentní | _Doplnit._ | _Doplnit._ + 1 %/bod Mastery |
| **Imp** | Warlock | 8 s + Mastery | _Doplnit._ | _Doplnit._ |
| **Hellhound** | Warlock | 10 s + Mastery | _Doplnit._ | _Doplnit._ |
| **Void Terror** | Warlock | 12 s + Mastery | _Doplnit._ | _Doplnit._ |

### Schopnosti bytostí
| Bytost | Schopnost | CD | Efekt |
|---|---|---|---|
| **Infernal** | *Hellfire Aura* | pasivní | Každou sekundu 15 % poškození všem nepřátelům v okruhu. Drží AoE threat i bez zásahu Summonera. |
| | *Impale* | 8 s | 180 % poškození jednomu cíli a **vysoký threat**. |
| **Kostlivec** | *Cleave* | 6 s | 90 % poškození až 3 cílům před sebou. |
| | *Bone Shield* | 20 s | Štít na sebe v hodnotě 20 % svého max. HP ([štíty](../../combat/shields.md)). |
| **Imp** | *Firebolt* | 2 s | 40 % poškození na dálku. Impové jsou ranged, drží se za Summonerem. |
| **Hellhound** | *Maul* | 7 s | 140 % poškození a **zpomalení** cíle o 30 % na 3 s. |
| **Void Terror** | *Void Slam* | 12 s | 200 % poškození v okruhu a cíle mají 6 s **−30 % Mitigation**. |

Poznámky:
- **Infernal** má jako jediný pasivní auru — tank pet musí držet aggro na skupině i bez příkazů.
- **Hellhound** a **Void Terror** přinášejí efekty, které Summoner sám nemá (zpomalení, snížení Mitigation).
- Schopnosti bytostí se počítají jako poškození bytosti, takže **threat jde bytosti**
  ([threat](../../combat/threat.md)).

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Hell Knight: Obrana démona
- Každý bod Mastery převádí část **defenzivních statů** Summonera na démona.
- Démon získá **1 % za bod** ze Summonerova **HP** a **Mitigation** (navíc ke svým vlastním statům).

```
démon.HP         += summoner.HP         × 1 % × Mastery
démon.Mitigation += summoner.Mitigation × 1 % × Mastery
```
| Mastery | Démon dostane navíc |
|---|---|
| 50 | 50 % HP a Mitigation Summonera |
| 100 | 100 % |

### Necromancer: Síla kostlivce
- **+1 % poškození kostlivce** za bod Mastery.

| Mastery | Bonus |
|---|---|
| 50 | +50 % |
| 100 | +100 % |

### Warlock: Trvání démonů
- **+0,1 s trvání** malých démonů za bod Mastery.

| Mastery | Trvání navíc |
|---|---|
| 20 | +2 s |
| 50 | +5 s |
| 100 | +10 s |

### Další pasivky
_Doplnit._

## Rizika a otevřené otázky
- **Staty bytostí:** mají vlastní pevné hodnoty, nebo škálují z Intelligence a vybavení Summonera?
  Bez toho nejde dopočítat žádné číslo výše.
- **Ovládání:** útočí bytosti samy (AI), nebo na cíl Summonera? Má hráč příkazy (útoč, následuj, stůj)?
- **Limit počtu:** kolik démonů může mít Warlock naráz (3 impové + pes + Void Terror = 5)?
- **Threat bytostí** mimo Hell Knighta: generuje kostlivec threat sobě, nebo Summonerovi?
- **Corpse Explosion** potřebuje mrtvoly — zůstávají po nepřátelích ve hře?
- **Dark Pact** platí HP; v PvP může být sebevražedné, zvážit strop.
