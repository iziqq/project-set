# Log

Chronologický, append-only záznam operací nad wiki (nejnovější dole).
Formát nadpisu: `## [YYYY-MM-DD] <ingest|query|lint|edit> | <název>`

## [2026-09-22] edit | Založení wiki
- Vytvořena struktura `raw/` + `wiki/`, stránky overview, game/concept, tech/stack, decisions/0001.
- Popis hry zatím chybí — čeká na první ingest.

## [2026-09-22] ingest | Základní popis hry
- Zdroj: `raw/2026-09-22-zakladni-popis-hry.md`
- Nové stránky: mechanics/classes, mechanics/talents, mechanics/stats, mechanics/equipment.
- Aktualizováno: overview, game/concept, index.
- Odhady (označené `(?)`): přiřazení resource a rolí k postavám, význam některých statů.
- Otevřené otázky: žánr / perspektiva, forma multiplayeru, struktura talentů, 2H zbraň vs. off-hand, vliv rarity na staty.

## [2026-09-22] ingest | Žánr, režimy, talenty, equip, role
- Zdroj: `raw/2026-09-22-zanr-rezimy-role.md`
- Nové stránky: game/game-modes, mechanics/economy, tech/networking.
- Aktualizováno: overview (pitch, pilíře), game/concept, mechanics/classes (role), mechanics/talents (strom), mechanics/equipment (2H, rarita, pevné staty, přetvoření 60 %), index.
- Rozpor: „4 staty na item“ vs. „vyšší rarita = více statů“, zapsáno v equipment → Rozpory.
- Stále nepotvrzeno: resource jednotlivých postav, perspektiva kamery.

## [2026-09-22] ingest | Staty
- Zdroj: `raw/2026-09-22-staty.md`
- Přepsána stránka mechanics/stats: primary (Strength, Agility, Intelligence, HP) a secondary staty s efekty za bod, CDR cap 60 %, základní crit 120 %.
- Rozpory: Range a Resource (zásoba) vypadly z listu, Intelligence je nová.
- Přidána sekce „K diskuzi“ s návrhy Clauda (mitigation, hit chance, balanc Agility, CDR, regen).

## [2026-09-22] ingest | Staty – upřesnění
- Zdroj: `raw/2026-09-22-staty-upresneni.md`
- mechanics/stats: vzorec Mitigation M/(M+100) pro fyzické i magické poškození; CDR asymptoticky k 60 %; Hit Chance +1 %/bod, cap 20; krit 120 % se zvedá talenty až na ~300 %; flat regen ponechán (singleplayer bonus → % později); Range statický na postavě; Resource max 100.
- Vyřešené rozpory: Range a Resource. Sekce „K diskuzi“ nahrazena rozhodnutími.
- Odvozeno (?): základní hit chance 80 %, K = 100 pro CDR.

## [2026-09-22] ingest | Hit Chance a CDR
- Zdroj: `raw/2026-09-22-hit-cdr.md`
- mechanics/stats: základní hit chance 60 %; CDR K = 50 (tabulka přepočítána).
- Rozpor: základ 60 % + 1 %/bod + cap 20 = jistý zásah nevychází, čeká na rozhodnutí.
- Rozpor vyřešen: Hit Chance +2 % za bod, cap 20 bodů = 100 % (varianta a).

## [2026-09-22] ingest | Equipment
- Zdroj: `raw/2026-09-22-equipment.md`
- mechanics/equipment přepsán: složení itemu (HP + primary + secondary), rarita (50/70/85/100 %, 1–3 secondary), násobitele slotů, matice hodnot, reroll (primary↔primary, secondary↔secondary, 1× na item, lze zrušit), sety 2/4/6/8, žádný item level, žádná omezení.
- Vyřešen rozpor „4 staty na item“: počet statů je 3–5 podle rarity.
- Potvrzeno ve stats: body nad hit cap bez efektu; Agi/Int přidávají body do secondary.
- Aktualizováno: classes (bez omezení vybavení), economy (reroll), index.
- Otevřené: základní hodnoty (100 %), talisman × rarita, „priorita“ primary statu, reroll HP.

## [2026-09-22] edit | Equipment – upřesnění
- Zdroj: `raw/2026-09-22-equipment.md` (sekce Upřesnění)
- Základní hodnoty se určí při návrhu itemů. Talisman má vždy přesně 1 secondary. Priorita primary statu pro dropy je omezená postavou. HP jde přetvořit. 2H má záměrně méně statů a silnější útoky. Cena přetvoření patří do ekonomiky.
- Aktualizováno: equipment, classes (omezení priority), economy (cena přetvoření).
- Stále otevřené: škálování talismanu podle rarity.
- Talisman: vlastní škála 150 / 200 / 250 / 300 % podle rarity. Otázka uzavřena.

## [2026-09-22] ingest | Warrior
- Zdroj: `raw/2026-09-22-warrior.md`
- Nová složka `wiki/classes/` (zapsána do CLAUDE.md) a stránka classes/warrior.
- Warrior: base HP 100 / Str 10 / Agi 3, priorita Str nebo Agi, Mastery podle role. Tank = Block Chance (15 % + 1 %/bod, blok −40 %, nad 100 % roste síla blocku přes křivku).
- Aktualizováno: mechanics/classes (tabulka stránek postav), mechanics/stats (Mastery), index.
- Otevřené: HP 100 = body, nebo životy? K pro sílu blocku, block bez štítu, DPS Mastery.

## [2026-09-22] edit | Warrior – upřesnění
- Zdroj: `raw/2026-09-22-warrior.md` (sekce Upřesnění)
- HP 20 bodů = 100 životů. Resource Rage. Tank vždy se štítem. Magické poškození nejde blokovat.
- Síla blocku: K opraveno z 50 (nepodložený odhad Clauda) na 100, stejně jako u Mitigation, podle zadání „výpočet jako u mitigation“.
- DPS Mastery = Bleed při critu (5 % + 1 %/bod z critu, tick 5 s, 15 s, stack +50 % a refresh).
- Otevřené: způsob stackování bleedu (exponenciální?), strop, mitigation na bleed.

## [2026-09-22] edit | Warrior – bleed
- Zdroj: `raw/2026-09-22-warrior.md` (sekce Upřesnění bleedu)
- Stack bleedu: každý další krit přičte 50 % aplikovaného bleedu (lineárně), obnoví 15 s. Mitigation se aplikuje. Vlastní tick timer (5 s) nezávislý na refreshi. Záměr: silný proti jednomu tanky cíli.
- Doplněno: každý Warrior má vlastní bleed; při vypršení mezi ticky proběhne částečný tick úměrný času od posledního ticku (1 s = 20 %).

## [2026-09-22] ingest | Paladin
- Zdroj: `raw/2026-09-22-paladin.md`
- Nová stránka classes/paladin: Mana, 18 HP bodů (90 životů), base staty podle role, priorita všech primary statů. Mastery: tank = stun útočníka 0,2 %/bod, DPS = +0,5 %/bod jako magický dmg, healer = štít 0,5 %/bod z healu.
- Aktualizováno: mechanics/classes, index.
- Otevřené: jak se volí role (base staty podle role), stun-lock v PvP a bossové, trvání a stackování štítu.
- Upřesnění Paladina: role se volí při výběru postavy (platí pro všechny, doplněno do classes a warrior). Stun bez cooldownu, bossové nejsou imunní, jen přímý dmg. Štít 18 s, sčítá se do 60 % max. HP, počítá se i z overhealu. DPS magický bonus z každého útoku, bez závislosti na kritu.
- Paladin: magický bonus DPS se počítá ze základu před kritem; nový heal obnoví trvání celého štítu na 18 s.

## [2026-09-22] ingest | Scout
- Zdroj: `raw/2026-09-22-scout.md`
- Nová stránka classes/scout: Energy, 15 HP bodů (75 životů), Agi 12, Str 6. Dvě DPS varianty: Hawkeye (ranged) a Adventurer (melee). Adventurer Mastery = efektivita Agility (200 = +100 %).
- Aktualizováno: classes (varianty rolí), index.
- Otevřené: Hawkeye Mastery, priorita primary statů, lineární škálování Adventurer.
- Scout: Hawkeye Mastery +0,3 % dmg s ranged zbraní/bod; priorita Agi/Str; varianty mají stejné base staty; Adventurer lineárně. Nová otázka v equipment: typy zbraní ranged/melee a dosah.
- Luk může nosit jen Scout (Hawkeye). Zapsáno jako výjimka z pravidla bez omezení v equipment.
- Luk jen pro Hawkeye (ne Adventurer). Range přesunut z postavy na zbraň, je to statická hodnota podle typu zbraně (stats, equipment).

## [2026-09-22] ingest | Wizard
- Zdroj: `raw/2026-09-22-wizard.md`
- Nová stránka classes/wizard: Mana, 70 životů, Int 15, Spirit 4, priorita jen Int. Varianty Pyromancer (Ignite DoT + přeskok) a Soultaker (+1 % dmg za nepřítele).
- Nový primary stat **Spirit** (1 % regenerace resource/s, není na itemech), zapsán do stats a equipment.
- Otevřené: výpočet a stackování Ignite, jak Mastery škáluje Soultaker, počítání nepřátel, Spirit vs. Resource Regen.
- Wizard upřesnění: Ignite 10 % + 0,5 %/bod celkem (4 ticky), stack jako bleed, přeskok při ticku jen na cíle bez Ignite (kopie zbytku). Soultaker 1 % + 0,5 %/bod za nepřítele v širokém okolí.
- Stats: návrh Clauda na odlišení Spirit (% max. resource, base + talenty) a Resource Regen (flat, itemy), max. resource zvyšitelný talenty. Čeká na schválení.
- Otevřené: řetězení přeskoku Ignite, síla Soultakera ve velkých skupinách.
- Wizard: řetězení přeskoku Ignite povoleno (může se rozšířit na celou skupinu). Soultaker snížen na 1 % + 0,1 %/bod za nepřítele.
- Spirit návrh schválen (stats). Soultaker v PvP počítá i hráče, možná vyšší PvP koeficient Mastery.

## [2026-09-22] ingest | Summoner
- Zdroj: `raw/2026-09-22-summoner.md`
- Nová stránka classes/summoner: speky Hell Knight (tank přes démona, může ho healovat), Necromancer (permanentní kostlivec, +1 % dmg/bod), Warlock (krátkodobí démoni, +0,1 s/bod). Base staty tank / DPS.
- classes: přidána obecná otevřená otázka aggro / threat.
- Otevřené: resource, priorita primary, vzorec Hell Knight Mastery, obecná mechanika summonů.
- Summoner: Mana, priorita jen Int, Hell Knight Mastery = 1 %/bod HP a Mitigation Summonera na démona. Parametry summonů určí jednotlivá kouzla.

## [2026-09-23] ingest | Monk
- Zdroj: `raw/2026-09-23-monk.md`
- Nová stránka classes/monk: tank (90 životů, Str 9, Agi 6) a DPS (80 životů, Str 8, Agi 9), priorita Str/Agi. Mastery: tank = 10 % + 0,5 %/bod poškození na štít (6 s), DPS = +0,1 %/bod za každý bod energy, který schopnost stojí.
- Aktualizováno: mechanics/classes, index.
- Otevřené: resource, zda je štít z poškození způsobeného, nebo utrpěného; strmé škálování DPS Mastery.
- Monk upřesnění: resource Energy; štít z poškození, které Monk způsobí; štít se nesčítá (větší přepíše, menší obnoví trvání); strmé DPS škálování zůstává k pozdějšímu doladění.
- Nová stránka mechanics/shields: srovnání štítů Paladina a Monka.
- Štíty z různých zdrojů (Paladin + Monk) jsou samostatné vrstvy a sčítají se; pořadí spotřeby zůstává jako návrh.

## [2026-09-23] ingest | Shaman
- Zdroj: `raw/2026-09-23-shaman.md`
- Nová stránka classes/shaman: Mana, priorita jen Int. Witch Doctor (heal, 80 životů, Int 8, Spirit 9; Mastery 12 % + 0,1 %/bod poškození jako heal na nejzraněnější cíl) a Voodoo Master (DPS, Int 10, Spirit 7; Mastery Voodoo Doll 10 % + 0,05 %/bod přenosu).
- Aktualizováno: mechanics/classes, index.
- Otevřené: cíl healu (i Shaman sám?), aplikace a trvání Voodoo Doll, řetězení mezi loutkami.
- Shaman upřesnění: heal míří na nejnižší % HP včetně Shamana, má velký dosah. Voodoo Doll je jedno kouzlo, jen 1 cíl, trvá do smrti cíle nebo přeznačení.
- Shaman: overheal se neřeší (propadne); přenos Voodoo Doll se nepočítá, když je hlavní cíl zároveň loutka.

## [2026-09-23] ingest | Cleric
- Zdroj: `raw/2026-09-23-cleric.md`
- Nová stránka classes/cleric: 3 speky — Mind Bender (DPS, debuff Insane: redukce dmg cíle 5 %/stack do 15 %, Mastery +0,1 % dmg i redukce za stack, strop redukce 40 %), Prophet (buffer, Spirit 11, Mastery +0,1 % síly buffů), Bishop (heal, Echo 0,5 %/bod, max 60 %).
- Aktualizováno: mechanics/classes (+ otázka na nevyužité resource Hope/Darkness), index.
- Otevřené: resource Clerica, počet a trvání stacků Insane, seznam buffů Propheta, pravidla Echa.
- Cleric upřesnění: Mana, priorita jen Int. Insane max 3 stacky, redukce 5 % + 0,1 %/bod do 13,3 % za stack (39,9 % celkem), trvání 30 s s obnovou. Prophet: buffy % dmg, Holy Fire, healovací aura (k domyšlení). Echo může skočit i na hlavní cíl.
- Nová otázka: Hope a Darkness nepoužívá žádná postava.
- Enum Resource zkrácen na Mana Points / Rage / Energy. Hope a Darkness vyřazeny (nikdo je nepoužíval).

## [2026-09-23] lint | Kontrola wiki
- Odstraněna zastaralá tvrzení: „resource je jen odhad“ (classes), „přiřazení k postavám nepotvrzeno“ (stats), Wizard „Mastery (upřesnit)“.
- Zavřeny vyřešené otázky v classes (resource, priorita primary statů).
- classes: nová srovnávací tabulka base statů všech postav a speků.
- overview: aktualizován stav (8 postav hotovo, seznam chybějícího), doplněn odkaz na štíty, datum.
- index: doplněny chybějící raw zdroje (štíty, resource cleanup), upřesněna shrnutí.
- Křížové odkazy: paladin → shields, classes → shields.

## [2026-09-23] ingest | Regenerace Rage/Energy, názvosloví
- Zdroj: `raw/2026-09-23-regenerace-role.md`
- Rage: +10 za autoattack. Energy: +5 za 3 s. Spirit 0 u Str/Agi postav je záměr. Zapsáno do stats (tabulka resource) a na stránky Warrior, Scout, Monk.
- Sjednoceno názvosloví: **Role** = Tank / DPS / Healer, **Spec** = pojmenovaná specializace. Upraveny všechny stránky postav a classes.
- classes: srovnávací tabulka má nyní sloupce Class / Spec / Role; chybějící názvy speků označeny.

## [2026-09-23] edit | ADR 0002–0004
- Nové ADR: 0002 bez item levelu, 0003 spec při výběru postavy, 0004 resource typy (Mana/Rage/Energy).
- Odkazy z equipment, classes, stats; index doplněn.
- CLAUDE.md: ADR píše Claude sám při zásadních rozhodnutích.

## [2026-09-23] ingest | Názvy speků
- Zdroj: `raw/2026-09-23-nazvy-speku.md`
- Doplněny chybějící názvy: Warrior = Temple Knight (tank) / Duelist (DPS); Paladin = Phoenix Knight (tank) / Warlord (DPS) / Shillien (healer); Monk = Tyrant (tank) / Wind Rider (DPS).
- Přejmenovány sekce Mastery na stránkách postav, aktualizovány classes, shields, index.
- Všech 15 speků má nyní název. Zbývají schopnosti.
- Přejmenování speků (původní názvy pocházely z Lineage 2): Warrior = Warden / Bleed Dancer; Paladin = Dawn Knight / Phoenix Rider / Light Bringer; Monk = Iron Turtle / Deadly Tiger.
- classes: přidán přehled počtu speků podle rolí (19 speků: 4 tank, 4 healer, 11 DPS). Opravuje dřívější zápis „15 speků“ v logu.

## [2026-09-23] ingest | Schopnosti – rozsah
- Zdroj: `raw/2026-09-23-schopnosti-rozsah.md`
- Nová stránka mechanics/abilities: 5–6 aktivních schopností na postavu + několik pasivek, šablona pro zápis schopnosti (cena, cooldown, cast time, dosah, cíl, efekt).
- Odkazy z classes, index, overview.
- Otevřené: schopnosti na postavu, nebo na spec; hotbar; globální cooldown; odemykání během běhu.

## [2026-09-25] edit | Složka na každou postavu
- Zdroj: `raw/2026-09-25-struktura-classes.md`
- `wiki/classes/<postava>.md` → `wiki/classes/<postava>/index.md`; ke každé postavě přidány prázdné `abilities.md` a `talents.md`.
- Přepsány všechny odkazy ve wiki, doplněny rozcestníky v mechanics/abilities a mechanics/talents.
- CLAUDE.md: aktualizovaná struktura repozitáře.

## [2026-09-25] edit | Mastery jako pasivní schopnost
- Zdroj: `raw/2026-09-25-mastery-pasivka.md`
- Popisy Mastery přesunuty z `classes/<postava>/index.md` do `classes/<postava>/abilities.md` jako „Mastery pasivky (základní pasivka speku)“; v index zůstal odkaz.
- Aktualizovány odkazy v shields, mechanics/abilities, mechanics/stats.
- stats: popis statu Mastery přeformulován na „zvyšuje sílu pasivní schopnosti postavy“ + nová sekce Mastery s odkazy na pasivky jednotlivých speků (zdroj `raw/2026-09-25-mastery-stat-popis.md`).

## [2026-09-25] edit | Rozpuštění mechanics/ do sekcí
- Zdroj: `raw/2026-09-25-struktura-sekce.md`
- `mechanics/classes.md` → `classes/index.md`, `mechanics/abilities.md` → `classes/abilities.md`.
- Nové sekce: `stats/`, `equipment/`, `talents/`, `economy/`, `combat/` (shields). Složka `mechanics/` zrušena.
- Přepsány všechny odkazy (kontrola: žádný rozbitý), aktualizován index a CLAUDE.md (+ pravidlo: nová sekce = vlastní složka s index.md).
- `talents/index.md` → `classes/talents.md` (obecná pravidla talentů k postavám), složka `talents/` zrušena. Index a CLAUDE.md aktualizovány.

## [2026-09-25] edit | Složky slotů v equipment
- Zdroj: `raw/2026-09-25-equipment-slozky.md`
- Uživatel vytvořil složky heads, chests, gloves, belts, legs, boots, rings, earrings, weapons, offhands, talismans.
- Do každé doplněn `index.md` se slotem, násobitelem slotu a prázdnou tabulkou itemů (weapons má navíc typ zbraně a Range, talismans vlastní škálu).
- equipment/index.md dostal rozcestník, index a CLAUDE.md aktualizovány.

## [2026-09-25] edit | Sekce combat
- Zdroj: `raw/2026-09-25-combat.md`
- Nové stránky: combat/index (rozcestník + nevyřešené: aggro, autoattack, smrt), combat/damage (pořadí výpočtu, typy poškození, block, mitigation), combat/effects (DoT bleed/ignite, debuffy Insane a Voodoo Doll, buffy Propheta, stun).
- Společná pravidla DoT vytažena z Warriora a Wizarda (tick timer, částečný tick, instance na dvojici cíl–zdroj).
- Aggro přesunuto z classes do combat; stats odkazuje na damage. Index a CLAUDE.md aktualizovány.
- combat/effects: DoT od různých hráčů se sčítají bez omezení, žádný strop na počet efektů na cíli, žádné diminishing returns na CC (stun má být silný). Otevřená zůstává čitelnost UI.
- Odhad počtu současných efektů na cíli: ~10, ne 20 — UI to zvládne jednoduchou lištou ikon.

## [2026-09-25] edit | Návrh schopností Warriora
- Zdroj: `raw/2026-09-25-warrior-ability-zadani.md`
- Do `classes/warrior/abilities.md` doplněno 6 aktivních schopností pro Wardena (Shield Bash, Challenge, Iron Stance, Bulwark, Punish, Last Stand) a 6 pro Bleed Dancera (Gash, Blade Dance, Hemorrhage, Frenzy, Bloodthirst, Blood Feast). Označeno jako **návrh Clauda, čeká na schválení**.
- Návrh je psaný per spec → otázka „schopnosti na postavu, nebo na spec“ v classes/abilities upravena.

## [2026-09-25] ingest | Threat systém a AoE pro tanky
- Zdroj: `raw/2026-09-25-threat-aoe.md`
- Nová stránka combat/threat: threat z poškození a healu, aggro má nejvyšší threat, tank spec generuje 10×.
- Pravidlo „každý tank spec musí mít AoE schopnost“ zapsáno do classes/abilities a threat.
- Warriorův Punish předělán na AoE (80 % fyz + 40 % Mitigation), Challenge napojen na threat.
- Otevřené: jak funguje taunt vůči threatu, threat z healu, threat démona Hell Knighta, pokles threatu v čase.
- Taunt: ignoruje threat, vynutí cíl na 2 s a vynuluje threat tabulku nepřítele (threat.md, Challenge upraven z 5 s na 2 s).
- Threat: heal generuje threat u všech nepřátel v boji; démon Hell Knighta má vlastní threat; threat klesá o 10 % za sekundu. Nová poznámka: uniformní procentní pokles nemění pořadí — k rozhodnutí.
- Threat: taunt vynuluje tabulku všem hráčům; pokles 10 %/s platí až po 3 s bez generování threatu (varianta a). Obě otázky uzavřeny.
- Warrior: návrh schopností Wardena a Bleed Dancera předběžně odsouhlasen; zůstává ve stavu „návrh“ k pozdějšímu ladění.

## [2026-09-25] edit | Návrh schopností Paladina
- Zdroj: `raw/2026-09-25-paladin-ability-zadani.md`
- `classes/paladin/abilities.md`: 6 schopností pro Dawn Knighta (Dawn Strike, Consecration, Call of Dawn, Judgment, Aegis, Undying Light), 6 pro Phoenix Ridera (Flame Lance, Phoenix Dive, Ember Brand, Wingbeat, Solar Flare, Rebirth Flame), 6 pro Light Bringera (Dawnlight, Radiance, Guardian Light, Purify, Beacon, Second Dawn). Stav: návrh.
- Upozornění: Paladin má Spirit 0, ale používá Manu → nová otevřená otázka na jeho stránce.
- Nová otázka v combat/effects: dají se debuffy odstraňovat (Purify)?
- Paladin: Guardian Light nahrazen pasivkou Divine Spark (5 % max. Many při způsobeném poškození). Light Bringer má 5 aktivních + Mastery pasivku + Divine Spark.
- Divine Spark: 5 % Many za každý zásah včetně autoattacků. Nové obecné pravidlo v combat/index: během sesílání kouzla nelze autoattackovat; autoattack krmí resource (Rage +10, Divine Spark +5 % Many).
- Paladin nemá Spirit (rozhodnuto). Manu doplňuje Resource Regen z itemů a u Light Bringera Divine Spark; zapsáno v paladin/index, abilities a stats. Otázka uzavřena.
- Divine Spark rozšířen na všechny speky Paladina (nahrazuje chybějící Spirit: Mana se doplňuje bojem).

## [2026-09-25] edit | Návrh schopností Summonera
- Zdroj: `raw/2026-09-25-summoner-ability-zadani.md`
- `classes/summoner/abilities.md`: Hell Knight (Summon Infernal, Hellfire Roar = AoE + taunt, Infernal Mend, Soul Link, Dark Pact, Abyssal Chains), Necromancer (Raise Skeleton, Bone Spear, Command: Rend, Corpse Explosion, Death Coil, Soul Harvest), Warlock (Summon Imps/Hellhound/Void Terror, Shadow Bolt, Sacrifice, Demonic Surge). Stav: návrh.
- Přidána tabulka vyvolaných bytostí s prázdnými staty a seznam rizik (staty bytostí, ovládání, limit počtu, threat, mrtvoly pro Corpse Explosion).
- Summoner: doplněny vlastní schopnosti vyvolaných bytostí (Hellfire Aura, Impale, Cleave, Bone Shield, Firebolt, Maul, Void Slam) + otázka, zda je spouští AI nebo hráč.
- Summoner: schopnosti bytostí spouští AI automaticky (rozhodnuto), návrh předběžně odsouhlasen.

## [2026-09-25] edit | Návrh schopností Scouta
- Zdroj: `raw/2026-09-25-scout-ability-zadani.md`
- `classes/scout/abilities.md`: Hawkeye (Aimed Shot, Piercing Arrow, Hunter's Mark, Rain of Arrows, Disengage, Second Wind), Adventurer (Twin Strike, Shadowstep, Whirl, Exposing Cut, Adrenaline, Evasion). Stav: návrh.
- Rizika: těsná Energy ekonomika (+5/3 s), Evasion zavádí snižování Hit Chance útočníkům, cílení na plochu.

## [2026-09-25] edit | Návrh schopností Wizard, Monk, Shaman, Cleric
- Zdroj: `raw/2026-09-25-zbyle-ability-zadani.md`
- Wizard: Pyromancer (Fireball, Flame Wave, Detonate, Immolate, Blink, Firestorm), Soultaker (Soul Lash, Dark Nova, Drain Souls, Soul Tether, Void Step, Harvest).
- Monk: Iron Turtle (Palm Strike, Sweeping Kick, Challenging Shout, Turtle Stance, Chi Barrier, Stone Skin), Deadly Tiger (Tiger Claw, Roaring Fist, Flurry, Leaping Strike, Inner Fire, Meditate).
- Shaman: Witch Doctor (Spirit Bolt, Healing Totem, Hex, Spirit Surge, Cleansing Waters, Ancestral Guard), Voodoo Master (Voodoo Doll, Curse Bolt, Pin Needles, Plague, Soul Swap, Ritual of Pain).
- Cleric: Mind Bender (Mind Spike, Psychic Scream, Shatter Mind, Confusion, Mind Barrier, Insanity Wave), Prophet (Blessing of Wrath, Holy Fire, Shield of Faith, Aura of Renewal, Prophecy, Divine Intervention), Bishop (Mend, Greater Mend, Circle of Healing, Sanctuary, Absolution, Martyr).
- Všech 19 speků má návrh schopností. Otevřená rizika zapsána u jednotlivých postav.

## [2026-09-25] ingest | Prophet – autoattack build
- Zdroj: `raw/2026-09-25-prophet-autoattack.md`
- Prophet je sám o sobě slabý **záměrně**; sólo hratelnost řeší talentová větev na autoattack (běžná zbraň, talent přepočítá Intelligence na poškození ze zbraně).
- Zapsáno do cleric/talents (nová sekce), cleric/abilities (poznámka i riziko) a classes/talents jako obecné pravidlo: talenty smí měnit škálování statů a sólo roli postavy.
- Confusion: cíl 3 s útočí na nejbližší nepřátelský cíl, ponecháno i v PvP jako zábavná interakce; doplněno do combat/effects (CC).
- Confusion: zmatený cíl ztrácí i ovládání pohybu, i v PvP. Poznámka, že jde o nejsilnější CC ve hře.

## [2026-09-25] ingest | Rozhodnutí k rizikům schopností
- Zdroj: `raw/2026-09-25-ability-rozhodnuti.md`
- Divine Intervention (Prophet) i Last Stand (Warden) zůstávají oba. Opravena chyba v zápisu: duplicita byla s Last Standem, ne s Undying Light (ten je heal 30 % HP).
- Prophecy (zaručený krit) schválena jako žádoucí kombo s kritovými speky.
- Ignite vzniká **jen z přímých zásahů**; DoT tiky neaplikují další efekty — zapsáno u Wizarda i jako obecné pravidlo v combat/effects.
