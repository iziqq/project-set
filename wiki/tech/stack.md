# Tech stack

> Související: [0001 — Godot + C#](../decisions/0001-godot-csharp.md)

- **Engine:** Godot 4 (.NET build)
- **Jazyk skriptů:** C# (.NET 8+); GDScript jen výjimečně (nástroje v editoru, prototypy)
- **IDE:** JetBrains Rider
- **Verzování:** git, `.godot/`, `bin/`, `obj/` a buildy jsou ignorované

## Struktura projektu (plán)
```
project.godot
ProjectSet.csproj / ProjectSet.sln
scenes/      # .tscn scény
scripts/     # C# skripty (namespace ProjectSet.*)
assets/      # grafika, zvuky, fonty
raw/         # zdroje pro wiki (neměnné)
wiki/        # LLM Wiki
```
