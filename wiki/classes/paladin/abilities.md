# Paladin — schopnosti

> Související: [Paladin](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Čísla jsou první nástřel k ladění.
> Poškození = % z **fyzického poškození**, heal = % z **magického léčení** (obojí roste ze statů,
> viz [staty](../../stats/index.md)). Resource: **Mana** (max. 100).

### Dawn Knight (tank) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Dawn Strike** | 15 Mana | 6 s | 1 nepřítel | 120 % fyz. poškození. Základní útok na držení threatu. |
| 2 | **Consecration** | 25 Mana | 15 s | okolí (AoE) | Posvátná země na **6 s**: každou sekundu 40 % fyz. poškození všem nepřátelům v okruhu. Hlavní AoE threat ([threat](../../combat/threat.md)). |
| 3 | **Call of Dawn** | 10 Mana | 12 s | okolí | **Taunt**: nepřátelé v okruhu útočí 2 s na Dawn Knighta, threat se všem vynuluje. |
| 4 | **Judgment** | 20 Mana | 18 s | 1 nepřítel | 100 % fyz. poškození a **stun 2 s** (aktivní verze [Mastery pasivky](#dawn-knight-tank-stun-při-zásahu)). |
| 5 | **Aegis** | 35 Mana | 40 s | sám | **+150 % Mitigation** na 6 s. |
| 6 | **Undying Light** | 30 Mana | 60 s | sám | Vyléčí **30 % max. HP** rozložených do 4 s. |

Poznámky k návrhu:
- **Consecration** plní pravidlo „[každý tank spec musí mít AoE](../abilities.md#pravidla-pro-návrh)“.
- **Judgment** je aktivní stun, zatímco Mastery dává stun náhodně při obdrženém zásahu — obojí se sčítá,
  proto krátký CD 18 s.
- **Undying Light** dává tankovi vlastní přežití, aby nebyl závislý na healerovi (co-op i singleplayer).

### Phoenix Rider (DPS) — 6 schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Flame Lance** | 15 Mana | 5 s | 1 nepřítel | 160 % fyz. poškození (+ magický bonus z [Mastery](#phoenix-rider-dps-magické-poškození-navíc)). |
| 2 | **Phoenix Dive** | 25 Mana | 14 s | plocha | Skok na místo, 120 % fyz. poškození v malém okruhu. Mobilita + přísun. |
| 3 | **Ember Brand** | 20 Mana | 10 s | 1 nepřítel | Cíl dostává **+15 % magického poškození** po dobu 8 s. |
| 4 | **Wingbeat** | 20 Mana | 20 s | okolí | 80 % fyz. poškození a odhodí nepřátele od sebe. |
| 5 | **Solar Flare** | 35 Mana | 25 s | 1 nepřítel | 250 % fyz. poškození, ale **jako magické** — nedá se [blokovat](../../combat/damage.md#block). |
| 6 | **Rebirth Flame** | 40 Mana | 60 s | sám | 8 s se **20 % způsobeného magického poškození** vrací jako heal. |

Poznámky k návrhu:
- Spec staví na tom, že část poškození je magická: **Ember Brand** a **Solar Flare** to zesilují,
  **Rebirth Flame** z toho dělá přežití.
- Magické poškození nejde blokovat, takže Phoenix Rider je dobrý proti tankům se štítem (PvP).

### Light Bringer (healer) — 5 aktivních schopností
| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Dawnlight** | 15 Mana | — | 1 spoluhráč | Heal 150 % magického léčení (+ štít z [Mastery](#light-bringer-healer-štít-z-healu)). |
| 2 | **Radiance** | 30 Mana | 12 s | okolí | Heal 100 % všem spoluhráčům v okruhu. |
| 3 | **Purify** | 15 Mana | 15 s | 1 spoluhráč | Odstraní jeden [debuff](../../combat/effects.md). |
| 4 | **Beacon** | 25 Mana | 30 s | sám | 12 s se **30 % způsobeného poškození** Light Bringera mění na heal nejzraněnějšímu spoluhráči. |
| 5 | **Second Dawn** | 50 Mana | 120 s | 1 spoluhráč | Okamžitý heal za **50 % max. HP** cíle. |

Poznámky k návrhu:
- **Dawnlight** je základní heal bez cooldownu; každý heal přidává štít přes Mastery.
- **Beacon** dává healerovi něco na práci, když nemá co léčit — a generuje threat ([threat](../../combat/threat.md)).
- **Second Dawn** je záchrana tanka; pokud budou v roguelike běhu vzkříšení, patří sem.
- Místo aktivního štítu má Light Bringer pasivku **[Divine Spark](#divine-spark--všechny-speky-paladina)**
  (má ji každý Paladin) — štíty už dává jeho [Mastery pasivka](#light-bringer-healer-štít-z-healu)
  z každého healu.

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Dawn Knight (tank): Stun při zásahu
- Když Paladin dostane poškození, má šanci **omráčit (stun) útočníka na 2 s**.
- Šance = **0,2 % za bod Mastery** (základ 0 % (?)).
- Spouští se jen **přímým poškozením** (ne DoT ticky).
- **Žádný interní cooldown ani diminishing returns**, ani v PvP — stun má být záměrně silný.
  Každá postava má být silná proti někomu; rychlí útočníci jsou proti Dawn Knightovi v nevýhodě.
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
- Magické poškození snižuje Mitigation cíle ([staty](../../stats/index.md#mitigation)).

| Mastery | Bonus |
|---|---|
| 20 | +10 % jako magické |
| 50 | +25 % |
| 100 | +50 % |

### Light Bringer (healer): Štít z healu
Srovnání se štítem Monka: [štíty](../../combat/shields.md).
- Každý heal aplikuje na cíl **štít (absorb)** v hodnotě **0,5 % za bod Mastery** z hodnoty healu.
- Příklad: heal za 200, 40 Mastery → štít 20 % = 40 absorb.
- Počítá se **i z overhealu** (plná hodnota healu) — výjimka, jinde se overheal neřeší.
- Trvání **18 s**. Každý nový heal obnoví trvání **celého** štítu na 18 s.
- Štíty se **sčítají**, maximálně do **60 % max. HP cíle**.

### Další pasivky

#### Divine Spark — všechny speky Paladina
- Když Paladin způsobí **poškození** nepříteli, doplní si **5 % max. Many**.
- Počítá se za **každý zásah** včetně autoattacků. Není to přemrštěné, protože Paladin nemá rychlé
  útoky a **během sesílání kouzla nemůže autoattackovat**
  ([autoattack](../../combat/index.md#autoattack)).
- Nahrazuje Paladinovi chybějící [Spirit](../../stats/index.md#primary-staty): Manu si doplňuje
  bojem, ne čekáním.
- Dopad podle speku:
  - **Dawn Knight** tankuje a pořád útočí, takže má Many dost.
  - **Phoenix Rider** ji má prakticky pořád.
  - **Light Bringer** musí mezi healy útočit — dobře se to doplňuje s **Beaconem**,
    kde se poškození navíc mění na heal.

## Rizika návrhu
- **Paladin nemá Spirit** (rozhodnuto) — Manu doplňuje Resource Regen z itemů a pasivka
  **Divine Spark** (všechny speky). Manu tedy získává bojem; spec, který chvíli neútočí, ji nedoplňuje.
- **Purify** předpokládá, že debuffy jdou odstraňovat; v [efektech](../../combat/effects.md) to zatím není.
