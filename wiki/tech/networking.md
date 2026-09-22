# Síťování

> Zdroje: [raw/2026-09-22-zanr-rezimy-role](../../raw/2026-09-22-zanr-rezimy-role.md) · Související: [herní režimy](../game/game-modes.md), [tech stack](stack.md)

- Multiplayer (co-op i PvP) je **online**.
- Uděláme **malý vlastní server**.

## Otevřené otázky
- Architektura: dedicated server (headless Godot .NET build), nebo listen server (hostuje hráč)
  s malým serverem jen pro lobby a matchmaking?
- Autorita: server-authoritative (nutné kvůli PvP proti cheatům)?
- Technologie: Godot High-level Multiplayer API (ENet / WebSocket), nebo vlastní řešení?
- Kde se ukládají postavy a equip (server vs. lokálně), a tedy jak se chrání před úpravou?
- Hosting (VPS, kapacita)?
