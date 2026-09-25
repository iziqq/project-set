# Warrior — schopnosti

> Související: [Warrior](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Stav: návrh (předběžně odsouhlasen 2026-09-25).** Směr sedí, čísla i názvy se budou ladit
> při testování. Není to finální podoba.
> Poškození se počítá jako % z **fyzického poškození** postavy (to roste ze Strength a Agility,
> viz [staty](../../stats/index.md)). Rage: Warrior získává **+10 za autoattack**.

### Warden (tank) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Shield Bash** | 20 Rage | 8 s | 1 nepřítel | 120 % fyz. poškození, přeruší sesílání. Vyžaduje štít. |
| 2 | **Challenge** | 10 Rage | 12 s | okolí | **Taunt**: nepřátelé v okruhu útočí **2 s** na Wardena a jejich threat se vynuluje ([threat](../../combat/threat.md)). |
| 3 | **Iron Stance** | 30 Rage | 25 s | sám | **+100 % Mitigation** na 8 s. |
| 4 | **Bulwark** | 40 Rage | 45 s | sám | **Block chance 100 %** na 5 s. Síla blocku podle [Mastery](#warden-tank-block-chance). |
| 5 | **Punish** | 25 Rage | 10 s | **okolí (AoE)** | 80 % fyz. poškození **+ 40 % vlastní Mitigation** všem nepřátelům v okruhu. Hlavní nástroj na udržení aggra na skupině. |
| 6 | **Last Stand** | 0 Rage | 120 s | sám | 6 s nemůže klesnout pod **1 HP**. |

Poznámky k návrhu:
- **Challenge** staví na [threat systému](../../combat/threat.md); zbývá doladit, jak přesně taunt
  pracuje s threatem.
- **Punish** je zároveň **AoE schopnost Wardena** (povinná pro tank speky) a dává tankovi vlastní
  škálování poškození přes Mitigation, aby nebyl závislý jen na Strength.
- **Bulwark + Mastery**: při vysoké Mastery je 5 s prakticky nezranitelnosti vůči fyzickému
  poškození — možná bude potřeba zkrátit.

### Bleed Dancer (DPS) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Gash** | 20 Rage | 6 s | 1 nepřítel | 150 % fyz. poškození, **vždy kritický zásah** → vždy aplikuje [Bleed](#bleed-dancer-dps-bleed). |
| 2 | **Blade Dance** | 30 Rage | 12 s | okolí | 3 seky po 60 % fyz. poškození na všechny nepřátele v malém okruhu (každý sek může kritnout). |
| 3 | **Hemorrhage** | 25 Rage | 15 s | 1 nepřítel | Okamžitě způsobí poškození **3 ticků aktuálního bleedu** na cíli. Bleed zůstává. |
| 4 | **Frenzy** | 30 Rage | 30 s | sám | **+50 % Attack Speed** na 8 s (víc autoattacků = víc Rage i kritů). |
| 5 | **Bloodthirst** | 40 Rage | 20 s | 1 nepřítel | 200 % fyz. poškození, **+1 % za každé chybějící % HP** cíle (dobíjení). |
| 6 | **Blood Feast** | 20 Rage | 40 s | sám | 10 s se **20 % poškození vlastních bleedů** vrací jako heal. |

Poznámky k návrhu:
- **Gash** je hlavní nástroj na nastackování bleedu i při nízké Crit Chance.
- **Hemorrhage** může s vysokou Mastery být velmi silné — kandidát na první nerf.
- **Blood Feast** dává DPS speku vlastní přežití, aby nebyl závislý na healerovi.


## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

Mastery se liší podle role.

### Warden (tank): Block Chance
**Block Chance** je speciální stat jen pro Wardena.
- Úspěšný block sníží příchozí **fyzické** poškození o **40 %**. **Magické poškození blokovat nejde.**
- Vyžaduje **štít**.
- Šance na block: **15 %** bez Mastery a **+1 % za každý bod Mastery**.
  Při **85 Mastery** je block chance **100 %**.
- Body Mastery nad 100 % block chance zvyšují **sílu blocku** (40 % → víc). Použije se křivka
  jako u Mitigation, takže 100 % redukce se nikdy nedosáhne.

Vzorec (stejná křivka jako [Mitigation](../../stats/index.md#mitigation), K = 100):
```
blockChance    = min(15 % + 1 % × Mastery, 100 %)
nadbytek       = max(Mastery − 85, 0)
blockReduction = 40 % + 60 % × nadbytek / (nadbytek + K)      K = 100
```
| Mastery | Block chance | Redukce blocku |
|---|---|---|
| 0 | 15 % | 40 % |
| 45 | 60 % | 40 % |
| 85 | 100 % | 40 % |
| 135 | 100 % | 60 % |
| 185 | 100 % | 70 % |
| 285 | 100 % | 80 % |

### Bleed Dancer (DPS): Bleed
Každý **kritický zásah** aplikuje na cíl **Bleed** (fyzické poškození v čase).
**Záměr:** velmi silný proti jednomu cíli s hodně životy (boss, elitní mob).

- **Aplikovaný bleed** z jednoho kritu = **(5 % + 1 % × Mastery) × poškození kritického zásahu**.
- **První krit** na cíl bez bleedu nastaví tick na 100 % aplikovaného bleedu.
- **Každý další krit** přičte k ticku **50 % aplikovaného bleedu** (z nového kritu, ne ze současného
  bleedu na cíli). Růst je lineární, nový bleed se vždy přičítá a nic nepřepisuje.
- Každý krit **obnoví trvání** na **15 s**.
- Poškození bleedu snižuje **Mitigation** cíle.

Příklad (0 Mastery = 5 %, krity po 100):

| Krit # | Aplikovaný bleed | Tick (každých 5 s) |
|---|---|---|
| 1. | 5 | 5 |
| 2. | 5 → +2,5 | 7,5 |
| 3. | 5 → +2,5 | 10 |

S 20 Mastery (25 %) a krity po 100: 25 → 37,5 → 50…

#### Tick timer
- Bleed má **vlastní tick timer**, nezávislý na obnovování trvání. Tikne každých **5 s** od první
  aplikace. Nový krit **neresetuje** tick timer, jen prodlouží trvání (konec = teď + 15 s).
- Bez dalších kritů = 3 ticky (5., 10., 15. sekunda).
- Hráč, který kritne častěji než jednou za 5 s, tak bleed pořád tiká a zároveň ho zesiluje.
- **Poslední částečný tick:** když bleed vyprší mezi ticky, proběhne ještě jeden tick úměrný času
  od posledního ticku: `tick × (čas od posledního ticku / 5 s)`.

| Vyprší … před dalším tickem | Čas od posledního ticku | Poslední tick |
|---|---|---|
| 4 s | 1 s | 20 % |
| 3 s | 2 s | 40 % |
| 2 s | 3 s | 60 % |
| 1 s | 4 s | 80 % |

- Každý Warrior má na cíli **vlastní bleed**. Bleedy od různých hráčů se nesčítají do jednoho.

```
onCrit(critDmg):
    applied = (0.05 + 0.01 * mastery) * critDmg
    if bleed == null: bleed = new Bleed(tick = applied); bleed.tickTimer.start(5s)
    else:             bleed.tick += 0.5 * applied
    bleed.expiresAt = now + 15s

every 5s (tickTimer):   deal(bleed.tick, Physical)  // projde přes Mitigation
on expiresAt:           deal(bleed.tick * timeSinceLastTick / 5s, Physical); remove bleed

// bleed je klíčovaný (target, sourceWarrior), každý Warrior má vlastní instanci
```

### Další pasivky
_Doplnit._
