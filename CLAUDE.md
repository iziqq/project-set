# CLAUDE.md — Project Set

Hra **Project Set** v enginu **Godot 4 (.NET)**, skripty v **C#**.
Znalosti o hře (design, mechaniky, rozhodnutí) žijí v LLM Wiki v `wiki/`. **Než začneš pracovat
na čemkoli herním, přečti `wiki/index.md` a relevantní stránky.**

## Jazyk
- Komunikace s uživatelem a obsah wiki: **česky**.
- Kód, identifikátory, komentáře v kódu, commit zprávy: **anglicky**.

## Struktura repozitáře
```
CLAUDE.md        # tento soubor — konvence projektu + schéma wiki
raw/             # neměnné zdroje (poznámky, přepisy, reference, obrázky)
wiki/            # LLM Wiki — markdown stránky spravované Claudem
  index.md       # katalog všech stránek (vždy aktuální)
  log.md         # append-only chronologický log operací
  overview.md    # souhrn hry a aktuálního stavu
  game/          # koncept, příběh, svět, postavy
  mechanics/     # jednotlivé herní mechaniky a systémy
  classes/       # jedna stránka na postavu (base staty, Mastery, schopnosti)
  tech/          # architektura, stack, konvence kódu
  decisions/     # ADR — číslované záznamy rozhodnutí (NNNN-nazev.md)
```
Godot projekt (`project.godot`, `scenes/`, `scripts/`, `assets/`) zatím neexistuje — plán je v `wiki/tech/stack.md`.

## LLM Wiki (podle Karpathyho)

Tři vrstvy:
1. **`raw/`** — zdroje pravdy. Pouze čteš, nikdy neupravuješ ani nemažeš.
2. **`wiki/`** — kompilované znalosti. Píšeš a udržuješ ty; uživatel čte a opravuje.
3. **`CLAUDE.md`** — schéma: jak je wiki organizovaná a jak s ní pracovat.

### Operace
- **Ingest** („ingest raw/X“ nebo uživatel popíše něco nového o hře v chatu):
  1. Přečti zdroj, krátce shrň klíčové body uživateli a doptej se na nejasnosti.
  2. Zapracuj informace do **všech** dotčených stránek (typicky 1–10) — aktualizuj existující,
     nové vytvářej jen pro samostatné koncepty.
  3. Označ rozpory se staršími informacemi (sekce `## Rozpory`), neřeš je potichu.
  4. Aktualizuj `wiki/index.md` a připiš záznam do `wiki/log.md`.
  - Pokud uživatel popisuje hru přímo v chatu, nejdřív to ulož jako zdroj do `raw/YYYY-MM-DD-nazev.md`, pak ingestuj.
- **Query** (otázka na hru): vyhledej přes `index.md`, odpověz s odkazy na stránky. Pokud odpověď
  přinese novou hodnotnou syntézu (srovnání, analýza), nabídni její uložení jako novou stránku.
- **Lint** („lint wiki“): najdi rozpory mezi stránkami, zastaralá tvrzení, osiřelé stránky bez odkazů,
  zmíněné pojmy bez vlastní stránky, chybějící křížové odkazy a otevřené otázky. Navrhni opravy.

### Konvence stránek
- Názvy souborů: `kebab-case.md`, anglicky nebo česky bez diakritiky.
- Pod nadpisem řádek `> Zdroje: ... · Související: ...` s relativními odkazy.
- Odkazy mezi stránkami standardními relativními markdown linky (`[text](../game/concept.md)`).
- Nevyplněné části označ `_Doplnit._`, nejisté informace `(?)`.
- Nevymýšlej herní design — co uživatel neřekl, zapiš jako otevřenou otázku, ne jako fakt.
- Log: nadpis `## [YYYY-MM-DD] <ingest|query|lint|edit> | <název>` + odrážky se změnami.
- Rozhodnutí (ADR) v `decisions/`: Datum, Stav, Kontext, Rozhodnutí, Důsledky.

## Kódové konvence (C# / Godot)
- Godot 4 .NET build, .NET 8+, `Nullable` zapnuté.
- Namespace `ProjectSet.*` odpovídající složce ve `scripts/`.
- Třídy uzlů `public partial class X : Node...`; název souboru = název třídy (PascalCase).
- Soubory scén a zdrojů `snake_case` (`main_menu.tscn`).
- Signály jako C# `[Signal] delegate void XEventHandler(...)`; exportované pole přes `[Export]`.
- Preferuj kompozici (child nodes, resources) před hlubokou dědičností.
- `.godot/`, `bin/`, `obj/` se necommitují (viz `.gitignore`).

## Git
- Hlavní větev `main`. Commituj jen na požádání uživatele.
- Změny ve wiki commituj zvlášť od změn kódu, prefix `wiki:` (např. `wiki: ingest core loop notes`).
