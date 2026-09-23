# Paladin

> Zdroje: [raw/2026-09-22-paladin](../../raw/2026-09-22-paladin.md) · Související: [classes](../mechanics/classes.md), [staty](../mechanics/stats.md), [Warrior](warrior.md)

## Role
Jediná postava se všemi třemi rolemi:

| Spec | Role | Mastery |
|---|---|---|
| **Dawn Knight** | Tank | stun útočníka |
| **Phoenix Rider** | DPS | část poškození navíc jako magické |
| **Light Bringer** | Healer | štít z healu |
Roli si hráč volí **při výběru postavy** (platí pro všechny postavy, viz [classes](../mechanics/classes.md)). Base staty se liší podle role.

## Resource
**Mana** (Mana Points, max. 100)

## Base staty
| Stat | Dawn Knight | Phoenix Rider | Light Bringer |
|---|---|---|---|
| HP | 18 bodů (= 90 životů) | 18 bodů (= 90 životů) | 18 bodů (= 90 životů) |
| Strength | 15 | 11 | 0 |
| Agility | 0 | 4 | 0 |
| Intelligence | 0 | 0 | 15 |

Staty, které nejsou uvedené, jsou 0 (?).

## Priorita primary statu (dropy)
**Všechny**: Strength, Agility, Intelligence.

## Mastery

### Dawn Knight (tank): Stun při zásahu
- Když Paladin dostane poškození, má šanci **omráčit (stun) útočníka na 2 s**.
- Šance = **0,2 % za bod Mastery** (základ 0 % (?)).
- Spouští se jen **přímým poškozením** (ne DoT ticky).
- **Žádný interní cooldown ani diminishing returns**, ani v PvP. Záměr: každá postava má být silná
  proti někomu, rychlí útočníci jsou proti Paladin tankovi v nevýhodě.
- **Bossové nejsou imunní**, jinak by Paladin tank proti bossům ztratil smysl.

| Mastery | Šance na stun |
|---|---|
| 25 | 5 % |
| 50 | 10 % |
| 100 | 20 % |

### Phoenix Rider (DPS): Magické poškození navíc
- **Každý útok** způsobí navíc **0,5 % za bod Mastery** ze svého poškození jako **magické poškození**.
- Počítá se ze **základního poškození před kritem**. Příklad: útok 100, krit 120, 50 Mastery → bonus **50** (ne 60).
- Záměr: Phoenix Rider **nemá být závislý na kritu**. Bonus je stálý a spouští ho každý útok.
- Magické poškození snižuje Mitigation cíle ([staty](../mechanics/stats.md#mitigation)).

| Mastery | Bonus |
|---|---|
| 20 | +10 % jako magické |
| 50 | +25 % |
| 100 | +50 % |

### Light Bringer (healer): Štít z healu
Srovnání se štítem Monka: [štíty](../mechanics/shields.md).
- Každý heal aplikuje na cíl **štít (absorb)** v hodnotě **0,5 % za bod Mastery** z hodnoty healu.
- Příklad: heal za 200, 40 Mastery → štít 20 % = 40 absorb.
- Počítá se **i z overhealu** (plná hodnota healu) — výjimka, jinde se overheal neřeší.
- Trvání **18 s**. Každý nový heal obnoví trvání **celého** štítu na 18 s.
- Štíty se **sčítají**, maximálně do **60 % max. HP cíle**.

## Schopnosti
_Doplnit._

## Otevřené otázky
- Schopnosti.
