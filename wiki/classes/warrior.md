# Warrior

> Zdroje: [raw/2026-09-22-warrior](../../raw/2026-09-22-warrior.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md), [equipment](../mechanics/equipment.md)

## Role
Spec volí hráč při výběru postavy.

| Spec | Role | Poznámka |
|---|---|---|
| **Warden** | Tank | vyžaduje **Weapon + Shield** ([equipment](../mechanics/equipment.md)); bez štítu neblokuje |
| **Bleed Dancer** | DPS | bleed z kritických zásahů |

## Resource
**Rage** (max. 100). Generuje se **+10 za každý autoattack**, ne přes Spirit (Warrior má Spirit 0).

## Base staty
| Stat | Hodnota |
|---|---|
| HP | 20 bodů (= **100 životů**) |
| Strength | 10 |
| Agility | 3 |
| Intelligence | 0 (?) |
| ostatní | _Doplnit._ |

## Priorita primary statu (dropy)
Warrior si může zvolit **Strength** nebo **Agility**.

## Mastery
Mastery se liší podle role.

### Warden (tank): Block Chance
**Block Chance** je speciální stat jen pro Wardena.
- Úspěšný block sníží příchozí **fyzické** poškození o **40 %**. **Magické poškození blokovat nejde.**
- Vyžaduje **štít**.
- Šance na block: **15 %** bez Mastery a **+1 % za každý bod Mastery**.
  Při **85 Mastery** je block chance **100 %**.
- Body Mastery nad 100 % block chance zvyšují **sílu blocku** (40 % → víc). Použije se křivka
  jako u Mitigation, takže 100 % redukce se nikdy nedosáhne.

Vzorec (stejná křivka jako [Mitigation](../mechanics/stats.md#mitigation), K = 100):
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

## Schopnosti
_Doplnit._ (dořeší se později)

## Otevřené otázky
- Schopnosti.
