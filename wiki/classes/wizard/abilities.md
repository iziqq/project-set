# Wizard — schopnosti

> Související: [Wizard](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Poškození = % z **magického poškození** (Intelligence).
> Resource: **Mana** (max. 100), regenerace přes **Spirit 4**.

### Pyromancer (DPS) — 6 schopností
Každý zásah zapaluje cíl ([Ignite](#pyromancer-ignite)), oheň se šíří na cíle, které nehoří.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Fireball** | 20 Mana | 3 s | 1 nepřítel | 160 % poškození. Základní kouzlo, zakládá Ignite. |
| 2 | **Flame Wave** | 30 Mana | 12 s | kužel | 140 % poškození všem v kuželu — rozseje Ignite na skupinu. |
| 3 | **Detonate** | 25 Mana | 15 s | 1 hořící cíl | Cíl vybuchne za 150 % v okruhu. **Ignite na něm zůstává.** |
| 4 | **Immolate** | 25 Mana | 20 s | sám (aura) | 8 s: každou sekundu 25 % poškození všem nepřátelům v okruhu. |
| 5 | **Blink** | 10 Mana | 18 s | sám | Přemístí se na krátkou vzdálenost. Jediný únik (70 životů). |
| 6 | **Firestorm** | 45 Mana | 40 s | plocha | 10 s hoří vybrané místo: 60 % poškození za sekundu. |

Poznámky: **Flame Wave** a **Immolate** jsou nástroje na rozšíření Ignite; **Detonate** je burst na
jeden cíl. Spec je silný, když je nepřátel víc a Ignite má kam skákat.

### Soultaker (DPS) — 6 schopností
Poškození roste s počtem nepřátel v okolí ([Mastery](#soultaker-poškození-podle-počtu-nepřátel)).

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Soul Lash** | 15 Mana | 3 s | 1 nepřítel | 150 % poškození. |
| 2 | **Dark Nova** | 35 Mana | 20 s | okolí (AoE) | 180 % poškození všem kolem. |
| 3 | **Drain Souls** | 30 Mana | 15 s | okolí | Sesílá 4 s: 80 % za sekundu všem v okruhu, 10 % z toho se vrací jako heal. |
| 4 | **Soul Tether** | 20 Mana | 18 s | až 5 nepřátel | Spojí cíle na 8 s: **30 % poškození** jednoho z nich dostanou i ostatní. |
| 5 | **Void Step** | 10 Mana | 18 s | sám | Krátký teleport. |
| 6 | **Harvest** | 40 Mana | 60 s | sám | 10 s se bonus za nepřítele **zdvojnásobí**. |

Poznámky: **Soul Tether** a **Harvest** znásobují jeho princip „čím víc nepřátel, tím líp“.
**Drain Souls** je jediné přežití, ale drží ho uprostřed skupiny — riskantní se 70 životy.

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Pyromancer: Ignite
Pasivní schopnost **Ignite**: každý **přímý zásah** Wizarda zapálí cíl. Poškození v čase (tiky
Firestormu, Immolate ani samotného Ignite) nový Ignite neaplikuje.
Záměr: **multi-target** postava. Oheň se může postupně rozhořet na celou skupinu. Síla se doladí přepočtem.

- **Ignite (celkem)** = **(10 % + 0,5 % × Mastery) × poškození zásahu**, rozložené do 4 ticků
  (každých **0,5 s** po dobu **2 s**). Bez Mastery = **2,5 % za tick**.
- **Opakovaný zásah** funguje stejně jako [Warrior bleed](../warrior/abilities.md#bleed-dancer-dps-bleed): první zásah
  nastaví plnou hodnotu, každý další přičte 50 % nově aplikovaného Ignite a obnoví trvání na 2 s.
  Vlastní tick timer, při vypršení mezi ticky proběhne částečný tick. Každý Wizard má na cíli vlastní Ignite.

| Mastery | Ignite celkem | Za tick |
|---|---|---|
| 0 | 10 % | 2,5 % |
| 20 | 20 % | 5 % |
| 50 | 35 % | 8,75 % |
| 100 | 60 % | 15 % |

#### Přeskok (spread)
- Šance **1 % × Mastery** se zkouší **při každém ticku** („oheň se rozhoří a pak přeskočí“).
- Ignite **zůstane** na původním cíli a na nový cíl se **zkopíruje zbývající** Ignite (hodnota ticku
  i zbývající čas). Nevzniká nový Ignite z plné hodnoty.
- Přeskakuje se **jen na nepřátele bez Ignite** (v okolí (?)). Když žádný takový není, přeskok nenastane.
  Tím se zabrání cyklickému přeskakování 1 → 2 → 1 a nekonečnému stackování.
- **Řetězení je povolené:** i zkopírovaný Ignite může přeskakovat dál. Protože kopie nese jen
  zbývající čas, každá další generace je kratší a slabší.

### Soultaker: Poškození podle počtu nepřátel
Záměr: „master blaster“ proti velkým skupinám malých nepřátel.

- Bonus za každého nepřítele v okolí = **1 % + 0,1 % × Mastery**.
- **Okolí** = poměrně velký okruh kolem Wizarda (hodnota se určí).
- V **PvP** se počítají i nepřátelští hráči. Pro PvP možná vyšší koeficient Mastery, aby byl Soultaker dost silný (?).

```
dmgBonus = početNepřátel × (1 % + 0,1 % × Mastery)
```
| Mastery | Za nepřítele | 5 nepřátel | 10 nepřátel | 20 nepřátel |
|---|---|---|---|---|
| 0 | 1 % | +5 % | +10 % | +20 % |
| 20 | 3 % | +15 % | +30 % | +60 % |
| 50 | 6 % | +30 % | +60 % | +120 % |
| 100 | 11 % | +55 % | +110 % | +220 % |

### Další pasivky
_Doplnit._

## Rizika návrhu
- **Ignite vzniká jen z přímých zásahů** (rozhodnuto). Poškození v čase — tedy tiky Firestormu,
  Immolate i samotného Ignite — nový Ignite neaplikuje. Jinak by se oheň okamžitě rozšířil všude.
- **Harvest + Soultaker Mastery**: při 100 Mastery a 20 nepřátelích je bonus +440 % — kandidát na ladění.
