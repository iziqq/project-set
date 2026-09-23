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
