# Shaman — schopnosti

> Související: [Shaman](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Poškození i heal = % z **magického poškození / léčení** (Intelligence).
> Resource: **Mana** (max. 100), regenerace přes **Spirit** (9 u Witch Doctora, 7 u Voodoo Mastera).

### Witch Doctor (healer) — 6 schopností
Léčí tím, že **útočí**: 12 % + 0,1 %/bod Mastery z poškození jde jako heal na nejzraněnějšího.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Spirit Bolt** | 15 Mana | 3 s | 1 nepřítel | 140 % poškození → spouští heal z [Mastery](#witch-doctor-heal-z-poškození). |
| 2 | **Healing Totem** | 30 Mana | 20 s | plocha | Totem na 10 s: každé 2 s vyléčí 40 % všem spoluhráčům v okruhu. |
| 3 | **Hex** | 20 Mana | 15 s | 1 nepřítel | Cíl dává o **30 % méně poškození** po dobu 6 s. |
| 4 | **Spirit Surge** | 25 Mana | 18 s | 1 spoluhráč | Okamžitý heal 250 % na nejzraněnějšího spoluhráče. |
| 5 | **Cleansing Waters** | 20 Mana | 25 s | okolí | Heal 100 % všem v okruhu a odstraní jeden [debuff](../../combat/effects.md). |
| 6 | **Ancestral Guard** | 35 Mana | 60 s | okolí | 8 s dostávají spoluhráči v okruhu **+30 % účinnost healu**. |

Poznámky: většina healu přichází z útočení, proto má jen dva přímé healy. **Hex** je jeho příspěvek
k přežití skupiny.

### Voodoo Master (DPS) — 6 schopností
Přenáší část poškození na cíl s [Voodoo Doll](#voodoo-master-voodoo-doll).

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Voodoo Doll** | 20 Mana | 8 s | 1 nepřítel | Označí cíl jako loutku (vždy jen jeden). |
| 2 | **Curse Bolt** | 15 Mana | 3 s | 1 nepřítel | 150 % poškození. |
| 3 | **Pin Needles** | 25 Mana | 12 s | loutka | 200 % poškození přímo do loutky; 5 s se **přenos zdvojnásobí**. |
| 4 | **Plague** | 30 Mana | 18 s | 1 nepřítel | DoT: 40 % každé 2 s po dobu 10 s. |
| 5 | **Soul Swap** | 20 Mana | 25 s | 2 nepřátelé | Přenese všechny debuffy z hlavního cíle na loutku. |
| 6 | **Ritual of Pain** | 40 Mana | 45 s | sám | 8 s je přenos na loutku **100 %** místo 10 %. |

Poznámky: **Ritual of Pain** je jeho velký moment — po dobu 8 s dostává loutka plné poškození navíc.
**Soul Swap** funguje jen ve spojení s debuffy od spoluhráčů (Insane, Ignite, bleed).

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Witch Doctor: Heal z poškození
- Když Witch Doctor způsobí poškození, **12 %** z něj se použije jako **heal**.
- **Overheal se neřeší** (přebytek propadne).
- Cíl healu = spoluhráč s **nejnižším procentem HP** (počítá se i **Shaman sám**), v **dosahu**
  (dosah bude dostatečně velký).
- Každý bod Mastery přidá **+0,1 %**.

```
heal% = 12 % + 0,1 % × Mastery
```
| Mastery | Podíl na heal |
|---|---|
| 0 | 12 % |
| 50 | 17 % |
| 100 | 22 % |

### Voodoo Master: Voodoo Doll
- Debuff **Voodoo Doll** se aplikuje **jedním kouzlem** a je **vždy jen na jednom cíli**.
- Trvá, dokud cíl nezemře nebo dokud Shaman neoznačí jiný cíl.
- Cíl s Voodoo Doll dostává **10 %** poškození, které Shaman způsobí **hlavnímu cíli**.
- Když je **hlavní cíl zároveň Voodoo Doll**, žádný přenos se nepočítá.
- Každý bod Mastery přidá **+0,05 %**.

```
přenos% = 10 % + 0,05 % × Mastery
```
| Mastery | Přenos na Voodoo Doll |
|---|---|
| 0 | 10 % |
| 100 | 15 % |
| 200 | 20 % |

### Další pasivky
_Doplnit._

## Rizika návrhu
- **Ritual of Pain** fakticky zdvojnásobuje poškození na 8 s — silné hlavně u bossů s přidaným cílem.
- **Plague** a Pyromancerův Ignite dělají podobnou věc; hlídat, aby DoT efekty nebyly zaměnitelné.
