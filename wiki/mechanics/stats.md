# Staty

> Zdroje: [raw/2026-09-22-wizard](../../raw/2026-09-22-wizard.md), [raw/2026-09-22-zakladni-popis-hry](../../raw/2026-09-22-zakladni-popis-hry.md), [raw/2026-09-22-staty](../../raw/2026-09-22-staty.md), [raw/2026-09-22-staty-upresneni](../../raw/2026-09-22-staty-upresneni.md), [raw/2026-09-22-hit-cdr](../../raw/2026-09-22-hit-cdr.md) · Související: [classes](classes.md), [talenty](talents.md), [equipment](equipment.md)

Staty mají dvě úrovně: **Primary** (dávají bonusy do dalších statů) a **Secondary** (přímý efekt).
Každá [postava](classes.md) má specifické základní hodnoty. Staty přicházejí z postavy,
[talentů](talents.md) a [vybavení](equipment.md). Seznam není konečný.

**Filozofie balancu:** hodnoty jsou záměrně „volatilní“. Nastavíme je, otestujeme a podle
výsledku zmenšíme nebo zrušíme. Nic není definitivní.

## Primary staty
| Stat | Efekt za 1 bod |
|---|---|
| **Strength** | +2 fyzické poškození, +1 Mitigation |
| **Agility** | +1 fyzické poškození, +1 Attack Speed, +1 Crit Chance |
| **Intelligence** | +2 magické poškození / healing, +1 Cooldown Reduction |
| **HP** | +5 max. životů |
| **Spirit** | +1 % z max. resource za sekundu jako regenerace (jen base + talenty, ne itemy) |

**Spirit** není na itemech. Pochází jen z base statů postavy a talentů.
Při max. resource 100 je 1 Spirit = 1 resource/s, tedy stejně jako 1 bod Resource Regen.

Bonusy do secondary statů se počítají v **bodech** daného statu (např. 1 Agility = 1 bod Crit
Chance = +0,5 %; 1 Intelligence = 1 bod CDR, počítaný přes vzorec).

## Secondary staty
| Stat | Efekt | Limit / poznámka |
|---|---|---|
| **Crit Chance** | +0,5 % šance na krit za bod | hodnota se může snížit při balancování |
| **Crit Damage** | +1 % síly kritu za bod | viz [Krit](#krit) |
| **Hit Chance** | +2 % šance zasáhnout za bod | **cap 20 bodů = vždy zasáhne**, viz [Hit Chance](#hit-chance) |
| **Attack Speed** | +2 % rychlosti útoku za bod | |
| **Mastery** | zesílí specifické kouzlo / pasivku | **jiné pro každou postavu i roli**, každý spec má vlastní, viz [classes](classes.md) |
| **Cooldown Reduction** | snižuje cooldowny | **asymptoticky k 60 %**, viz [vzorce](#vzorce) |
| **HP Regen** | +1 HP za sekundu za bod | flat, viz [Regenerace](#regenerace) |
| **Resource Regen** | +1 resource za sekundu za bod | flat, platí pro **všechny** typy resource včetně Rage |
| **Mitigation** | snižuje přijaté poškození (fyzické **i magické**) | nikdy 100 %, viz [vzorce](#vzorce) |

## Statické staty
Nejsou rollované na itemech a nejde je přetvořit.

| Stat | Hodnota | Poznámka |
|---|---|---|
| **Range** | podle **zbraně** | statická hodnota zbraně ([equipment](equipment.md#range-zbraní)), případně výjimečně upraví talent |
| **Resource (max)** | **100** (default) | typ viz níže |

## Vzorce

### Mitigation
```
redukce = M / (M + K)        K = 100
přijaté poškození = poškození × (1 − redukce)
```
| Mitigation | Redukce |
|---|---|
| 25 | 20 % |
| 50 | 33 % |
| 100 | 50 % |
| 200 | 67 % |
| 400 | 80 % |

Platí pro fyzické i magické poškození. `K` je laditelná konstanta.

### Cooldown Reduction
Stejný princip jako Mitigation, jen strop je 60 % a nikdy se ho nedosáhne:
```
CDR = 60 % × P / (P + K)     K = 50
```
| CDR body | Snížení cooldownu |
|---|---|
| 25 | 20 % |
| 50 | 30 % |
| 100 | 40 % |
| 200 | 48 % |
| 400 | 53 % |

Původně „1 bod = 1 %“. Vzorec to nahrazuje: u malých hodnot to vychází zhruba na 1 % za bod.
`K` je laditelná konstanta.

## Hit Chance
- Základní šance na zásah je **60 %**. Cap je **20 bodů = vždy zasáhne (100 %)**.
- Každý bod přidá **+2 %**: `hit = 60 % + 2 % × min(body, 20)`.
- **Záměr:** hráč se rozhoduje. Může riskovat minutí a místo Hit Chance vzít víc poškození.
  Tank nebo healer tento stat řešit nemusí.
- Body nad cap nemají efekt.
- Původně „1 za bod“ se základem 80 %. Změněno na základ 60 % a 2 % za bod (varianta a).

## Krit
- Základní krit = **120 %** normálního poškození.
- Crit Damage (+1 % za bod) a talenty můžou krit výrazně zvednout, u některých postav až na **~300 %**.

## Regenerace
- HP Regen a Resource Regen jsou zatím **flat za sekundu**.
- Resource Regen z itemů platí i pro Rage a Energy a přičítá se k jejich vlastní regeneraci
  (Rage z autoattacků, Energy 5 / 3 s).
- Plán: **singleplayer bonus**, ve kterém se flat regenerace mění na procentuální (detaily později).

## Spirit vs. Resource Regen
Navrhl Claude, uživatel schválil (2026-09-22).

| | **Spirit** (primary) | **Resource Regen** (secondary) |
|---|---|---|
| Zdroj | jen base staty postavy + talenty | itemy |
| Efekt | **% z max. resource** za sekundu | **flat** +1 / s |
| Identita | „vrozená“ regenerace postavy: casteři ji mají, Warrior 0 (Rage z boje) | volba buildu přes equip |
| Škálování | roste s **max. resource** | neroste |

- **Max. resource není pevných 100:** 100 je default. Talenty a Mastery můžou max. resource zvedat
  (např. „+50 max. Mana“). Spirit pak škáluje se zásobou, Resource Regen ne.
  Spirit je tak silný pro buildy „velká zásoba“, Resource Regen pro buildy „drahá kouzla často“.
- Spirit **nezvyšuje** Resource Regen z itemů a naopak, obě hodnoty se sčítají.

```
regen/s = maxResource × Spirit × 1 %  +  ResourceRegen × 1
```
Příklad: Wizard, 4 Spirit, max. Mana 150 (talent), 10 Resource Regen → 6 + 10 = 16 Mana/s.

## Resource (enum)
Typ zdroje, který postava spotřebovává na schopnosti:
**Mana Points, Rage, Energy**.

| Resource | Postavy | Jak se doplňuje |
|---|---|---|
| Mana Points | [Paladin](../classes/paladin.md), [Wizard](../classes/wizard.md), [Summoner](../classes/summoner.md), [Shaman](../classes/shaman.md), [Cleric](../classes/cleric.md) | **Spirit** (% z max. za sekundu) + Resource Regen z itemů |
| Rage | [Warrior](../classes/warrior.md) | **+10 Rage za každý autoattack** (Spirit 0) |
| Energy | [Scout](../classes/scout.md), [Monk](../classes/monk.md) | **+5 Energy za 3 s** (Spirit 0) |

Postavy na Strength / Agility mají **Spirit 0** záměrně: Rage a Energy se doplňují vlastním
způsobem, ne přes Spirit. Resource Regen z itemů se přičítá ke všem typům.

Původně byly v enumu i **Hope** a **Darkness**. Žádná postava je nepoužívá, proto byly vyřazeny ([ADR 0004](../decisions/0004-resource-typy.md)). Max. zásoba je 100 (default), talenty (a Mastery) ji můžou zvýšit, viz Spirit.

## Poznámky z diskuze
- Claude upozorňoval, že Agility škáluje 3 staty a může přerůst Strength. Uživatel čeká opačný
  efekt v PvP: hráči budou stavět Strength kvůli přežití (mitigation). Ověří se testováním.

## Otevřené otázky
- Singleplayer bonus: jak přesně se flat regenerace převede na %?
- Jak Mastery funguje u jednotlivých postav (řeší se u classes).

## Poznámky k implementaci
- `enum StatType`, `enum ResourceType`. Konverzní koeficienty (2 dmg / Str, 0,5 % / Crit bod,
  K konstanty, capy) držet v datech (Godot `Resource` / `.tres`), ne v kódu, aby šlo ladit balanc
  bez rekompilace.
- Pipeline: base staty postavy + talenty + equip → primary → odvozené secondary → vzorce (CDR,
  Mitigation) → finální hodnoty.
- Pořadí výpočtu poškození (návrh): base dmg schopnosti + bonus ze statů → hit roll → crit roll → Mitigation cíle.
