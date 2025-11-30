---
title: Wand Level 01 - Procedural Generation
category: scripts
---

# Wand Level 01 - Procedural Generation

This script defines parameters for the procedural generation of a "Level 01" wand in Noita. It leverages a shared procedural generation script to create the wand's properties.

## Core Generation Function

The primary function used is `generate_gun`, which is called with specific arguments to define the characteristics of this particular wand type.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural_better.lua")

generate_gun( 30, 1, false )
```

### `generate_gun` Parameters

*   **`30`**: This likely represents a base "power" or "rarity" value for the wand, influencing the types and quality of spells it can spawn.
*   **`1`**: This parameter could signify a specific "level" or "tier" for this wand generation, potentially affecting its complexity or the number of spell slots.
*   **`false`**: This boolean value might control whether certain advanced or experimental features are enabled for this wand generation.

## Key Attributes Influenced by Generation

While the specific attributes are determined by `gun_procedural_better.lua`, the `generate_gun` call influences:

*   **Spell Slots**: The number of spells the wand can hold.
*   **Recharge Time**: How quickly the wand can fire again.
*   **Cast Delay**: The time between casting spells within the wand.
*   **Mana Capacity**: The total mana the wand possesses.
*   **Spell Distribution**: The probability of certain spell types appearing on the wand.
*   **Perks/Modifiers**: Potential inherent bonuses or unique properties.
*   **Visuals/Audio**: The aesthetic and sound effects associated with the wand.