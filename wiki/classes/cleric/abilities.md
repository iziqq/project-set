# Cleric — schopnosti

> Související: [Cleric](index.md), [schopnosti (obecně)](../abilities.md), [talenty](talents.md)

5–6 aktivních schopností + pasivky. Šablona zápisu: [mechanics/abilities](../abilities.md#šablona-schopnosti).

## Aktivní schopnosti

> **Návrh Clauda, čeká na schválení.** Poškození i heal = % z **magického poškození / léčení**.
> Resource: **Mana** (max. 100), regenerace přes **Spirit** (7 Mind Bender, 11 Prophet, 9 Bishop).

### Mind Bender (DPS) — 6 schopností
Stacky **Insane** cíli snižují poškození a zvyšují to, které dostává.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Mind Spike** | 15 Mana | 3 s | 1 nepřítel | 140 % poškození, +1 stack [Insane](#mind-bender-insane). |
| 2 | **Psychic Scream** | 25 Mana | 18 s | okolí (AoE) | 120 % poškození a +1 stack Insane všem v okruhu. |
| 3 | **Shatter Mind** | 30 Mana | 15 s | 1 nepřítel | 150 % poškození **+60 % za každý stack Insane** na cíli. Stacky zůstávají. |
| 4 | **Confusion** | 20 Mana | 25 s | 1 nepřítel | Cíl **3 s útočí na nejbližší nepřátelský cíl**; v PvP hráč ztrácí i **ovládání pohybu**. |
| 5 | **Mind Barrier** | 20 Mana | 30 s | sám | Štít 200 % na 10 s ([štíty](../../combat/shields.md)). |
| 6 | **Insanity Wave** | 40 Mana | 40 s | sám | 10 s aplikují všechny jeho zásahy **2 stacky** Insane. |

Poznámky: spec je pomalý rozjezd (stacky) a pak velká odměna. **Confusion** je jediné CC,
které nepřítele nezastaví, ale obrátí — hodí se ve skupinách.

### Prophet (healer / buffer) — 6 schopností
Nehealuje ani nedamaguje přímo; **zesiluje ostatní**. Mastery zvyšuje sílu buffů o 0,1 %/bod.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Blessing of Wrath** | 25 Mana | 30 s | skupina | 15 s **+20 % poškození** všem spoluhráčům v okruhu. |
| 2 | **Holy Fire** | 20 Mana | 12 s | 1 spoluhráč | 8 s: zásahy cíle zapalují nepřátele (DoT 20 % z jeho poškození). |
| 3 | **Shield of Faith** | 25 Mana | 20 s | skupina | 8 s **+30 % Mitigation** všem spoluhráčům v okruhu. |
| 4 | **Aura of Renewal** | 30 Mana | 25 s | sám (aura) | 10 s: každou sekundu vyléčí **2 % max. HP** spoluhráčům v okruhu. |
| 5 | **Prophecy** | 15 Mana | 20 s | 1 spoluhráč | Následující útok cíle je **zaručený kritický zásah**. |
| 6 | **Divine Intervention** | 50 Mana | 120 s | 1 spoluhráč | 4 s cíl **nemůže klesnout pod 1 HP**. |

Poznámky: Prophet je „druhý healer“ jen díky auře — jeho hodnota je v buffech. V co-opu je nejsilnější
s velkou skupinou. **Sám o sobě je záměrně slabý** — sólo se hraje přes
[autoattack build z talentů](talents.md#prophet--autoattack-build).

### Bishop (healer) — 6 schopností
Klasický healer; každý heal se odráží [Echem](#bishop-echo) na druhého nejzraněnějšího.

| # | Název | Cena | CD | Cíl | Efekt |
|---|---|---|---|---|---|
| 1 | **Mend** | 15 Mana | — | 1 spoluhráč | Heal 160 %. Základní heal bez cooldownu. |
| 2 | **Greater Mend** | 30 Mana | 8 s | 1 spoluhráč | Heal 300 %, sesílání 2 s. |
| 3 | **Circle of Healing** | 35 Mana | 15 s | okolí | Heal 120 % všem spoluhráčům v okruhu. |
| 4 | **Sanctuary** | 30 Mana | 45 s | plocha | 8 s: spoluhráči v oblasti dostávají **o 30 % méně poškození**. |
| 5 | **Absolution** | 20 Mana | 20 s | 1 spoluhráč | Odstraní **všechny** debuffy z cíle. |
| 6 | **Martyr** | 25 Mana | 60 s | 1 spoluhráč | 8 s se **30 % poškození cíle** přesměruje na Bishopa. |

Poznámky: Echo znamená, že i single-target healy léčí dva lidi — Bishop je proto silný ve skupině,
zatímco na jednoho člověka (tank v co-opu) polovinu Echa promrhá.

## Pasivní schopnosti

<a id="mastery-pasivky-zakladni-pasivka-speku"></a>
### Mastery pasivky (základní pasivka speku)
Každý spec má jednu **základní pasivní schopnost** navázanou na stat
[Mastery](../../stats/index.md#secondary-staty). Body Mastery z [vybavení](../../equipment/index.md)
ji zesilují.

### Mind Bender: Insane
Každý zásah aplikuje na cíl stack debuffu **Insane**, **max. 3 stacky**.
- **Redukce poškození cíle** = **5 % za stack**, Mastery ji zvyšuje o **0,1 % za bod**,
  **max. 13,3 % za stack** (3 stacky = 39,9 %, prakticky 40 %).
  Strop je dosažen při **83 Mastery**.
- **Bonus poškození do cíle** = **0,1 % za bod Mastery za každý stack**.
- **Trvání stacku 30 s**, každá další aplikace obnoví trvání na 30 s.

```
redukce/stack = min(5 % + 0,1 % × Mastery, 13,3 %)
redukceCelkem = stacky × redukce/stack           (max. 39,9 % při 3 stacích)
dmgBonus      = stacky × 0,1 % × Mastery
```
| Mastery | Redukce / stack | Redukce (3 stacky) | Bonus dmg (3 stacky) |
|---|---|---|---|
| 0 | 5 % | 15 % | 0 % |
| 50 | 10 % | 30 % | +15 % |
| 83+ | 13,3 % (strop) | 39,9 % | +25 % a výš |
| 200 | 13,3 % (strop) | 39,9 % | +60 % |

Po dosažení stropu redukce roste dál už jen bonus poškození.

### Prophet: Síla buffů
- Každý bod Mastery zvýší **sílu buffů** o **0,1 %**.

| Mastery | Buffy silnější o |
|---|---|
| 50 | +5 % |
| 100 | +10 % |
| 200 | +20 % |

Plánované typy buffů (uživatel ještě domýšlí):
- procentuální **zvýšení poškození** spoluhráčům,
- krátkodobý buff na spoluhráče, který přidává **Holy Fire** (DoT na zasažené cíle),
- **aura** kolem Propheta s mírným healem.

### Bishop: Echo
- Každý heal se **odrazí (Echo)** na **druhý cíl s nejnižším procentem HP**.
- Síla Echa = **0,5 % za bod Mastery** z původního healu, **max. 60 %** (= 120 Mastery).
- Echo může skočit i **zpět na hlavní cíl** (např. když je zraněný jen jeden hráč).

| Mastery | Echo |
|---|---|
| 20 | 10 % |
| 60 | 30 % |
| 120+ | 60 % (strop) |

### Další pasivky
_Doplnit._

## Rizika návrhu
- **Confusion** obrací cíl proti jeho vlastním — **ponecháno i v PvP** včetně ztráty ovládání pohybu.
  Je to nejsilnější CC ve hře (3 s bez kontroly); při ladění PvP to bude první kandidát na zkrácení.
- **Prophecy** (zaručený krit) je záměrně silná u speků, které stojí na kritu
  ([Bleed Dancer](../warrior/abilities.md)) — schváleno jako žádoucí kombo pro co-op.
- **Divine Intervention** (Prophet) a **Last Stand** [Wardena](../warrior/abilities.md) dělají totéž
  (cíl neklesne pod 1 HP). **Necháváme obě** — ve skupině se často nepotkají a je to jediná pojistka,
  kterou Prophet nabízí. (Dawn Knightův *Undying Light* je něco jiného: heal 30 % max. HP.)
- **Prophet v singleplayeru** je slabý **záměrně**; sólo ho vytáhne autoattack build z talentů.
