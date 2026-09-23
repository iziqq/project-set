# Štíty (absorb)

> Zdroje: [raw/2026-09-22-paladin](../../raw/2026-09-22-paladin.md), [raw/2026-09-23-monk](../../raw/2026-09-23-monk.md), [raw/2026-09-23-stity](../../raw/2026-09-23-stity.md) · Související: [Paladin](../classes/paladin.md), [Monk](../classes/monk.md), [staty](stats.md)

Štít pohltí příchozí poškození, než ubyde HP. **Každý zdroj štítu má vlastní pravidla.**

## Štíty z různých zdrojů
Štíty z **různých zdrojů** (Light Bringer + Iron Turtle) jsou **samostatné vrstvy a sčítají se**. Pravidla
skládání (přepis, strop) platí vždy jen v rámci jednoho zdroje.

| | [Light Bringer (Paladin healer)](../classes/paladin.md#light-bringer-healer-štít-z-healu) | [Iron Turtle (Monk tank)](../classes/monk.md#iron-turtle-tank-štít-z-poškození) |
|---|---|---|
| Zdroj | heal na cíl (0,5 %/bod Mastery z healu, i z overhealu) | 10 % + 0,5 %/bod z poškození, které Iron Turtle způsobí |
| Cíl | healovaný spoluhráč | Iron Turtle sám |
| Trvání | 18 s | 6 s |
| Skládání | **sčítá se**, strop 60 % max. HP cíle | **nesčítá se**: větší přepíše, menší jen obnoví trvání |
| Obnovení trvání | nový heal obnoví celý štít na 18 s | ano |

## Otevřené otázky
- **Pořadí spotřeby vrstev:** návrh (?) — nejdřív se spotřebuje ta, která dřív vyprší, ať nic nepropadne.
- Zobrazení v UI (jedna lišta, nebo vrstvy)?
