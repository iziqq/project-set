# Efekty (buffy, debuffy, DoT, CC)

> Související: [souboj](index.md), [štíty](shields.md), [postavy](../classes/index.md)

Přehled efektů, které ve hře jsou. Detaily a vzorce jsou u postav, tady je **srovnání a společná pravidla**.

## DoT (poškození v čase)
| Efekt | Zdroj | Tick | Trvání | Stackování |
|---|---|---|---|---|
| **Bleed** | [Bleed Dancer](../classes/warrior/abilities.md#bleed-dancer-dps-bleed) (krit) | 5 s | 15 s | +50 % nově aplikované hodnoty, obnoví trvání |
| **Ignite** | [Pyromancer](../classes/wizard/abilities.md#pyromancer-ignite) (jen **přímé** zásahy) | 0,5 s | 2 s | jako bleed; navíc **přeskok** na cíle bez Ignite |
| **Holy Fire** | [Prophet](../classes/cleric/abilities.md) (buff na spoluhráče) | _Doplnit._ | _Doplnit._ | _Doplnit._ |

Společná pravidla (z bleedu a Ignite):
- Vlastní **tick timer**, který nová aplikace **neresetuje** — jen prodlouží trvání.
- Když efekt vyprší mezi ticky, proběhne **částečný tick** úměrný času od posledního ticku.
- Efekt je vázaný na dvojici **(cíl, zdroj)**: každý hráč má na cíli vlastní instanci.
- Instance od různých hráčů se **sčítají bez omezení** (dva Bleed Dancers na bossovi = dva plné bleedy).
- DoT snižuje **Mitigation** cíle.
- **DoT tiky neaplikují další efekty** (např. Ignite vzniká jen z přímých zásahů).

## Debuffy
| Debuff | Zdroj | Efekt | Trvání |
|---|---|---|---|
| **Insane** | [Mind Bender](../classes/cleric/abilities.md) | cíl dává méně poškození (max. 39,9 % při 3 stacích) a dostává víc | 30 s, obnovuje se |
| **Voodoo Doll** | [Voodoo Master](../classes/shaman/abilities.md) | přenáší 10 %+ poškození z hlavního cíle; jen **1 cíl** | do smrti cíle / přeznačení |

## Buffy
| Buff | Zdroj | Efekt |
|---|---|---|
| Buffy Propheta | [Prophet](../classes/cleric/abilities.md) | % poškození spoluhráčům, Holy Fire, healovací aura — _detaily doplnit_ |

Sílu buffů zvyšuje Mastery Propheta (+0,1 % za bod).

## Crowd control (CC)
| Efekt | Zdroj | Délka | Pravidla |
|---|---|---|---|
| **Confusion** | [Mind Bender](../classes/cleric/abilities.md) | 3 s | cíl útočí na nejbližší nepřátelský cíl; hráč **ztrácí i ovládání pohybu** (platí i v PvP) |
| **Stun** | [Dawn Knight](../classes/paladin/abilities.md) (0,2 %/bod při zásahu) | 2 s | **žádný interní cooldown ani diminishing returns**, ani v PvP; **bossové nejsou imunní**; spouští jen přímé poškození |

## Společná pravidla
- **Žádný strop na počet efektů** na jednom cíli (debuffy, DoT, buffy).
- **Žádné diminishing returns** na CC, ani v PvP — stun má být záměrně silný.
- DoT od různých zdrojů se sčítají bez omezení.

## Otevřené otázky
- **Odstraňování efektů:** dají se debuffy sundat (Purify Light Bringera)? Které ano a které ne?
- Zobrazení efektů v UI (ikony, počty stacků, zbývající čas). Reálný odhad je **max. ~10 efektů**
  na cíli, takže je zobrazí i jednoduchá lišta ikon.
