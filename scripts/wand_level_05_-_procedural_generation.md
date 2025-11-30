---
title: Wand Level 05 - Procedural Generation
category: scripts
---

# Wand Level 05 - Procedural Generation

This script defines parameters for the procedural generation of wands at level 05. It utilizes the `gun_procedural_better.lua` library to create wands with specific characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`100`**: This likely represents a base "power" or "rarity" value for the generated wands. Higher values generally lead to more potent or complex wands.
*   **`5`**: This parameter probably influences the number of spells or spell slots available on the generated wands. A value of 5 suggests wands with a moderate number of spellcasting capabilities.
*   **`false`**: This boolean likely controls whether the generated wands are "limited" or "unlimited" in their spellcasting capacity (e.g., mana regeneration or charge count). `false` suggests wands that are not inherently unlimited.

## Underlying Logic

The generation process is handled by the `gun_procedural_better.lua` script, which contains the core algorithms for creating procedural wands. This script likely defines various spell combinations, modifiers, and statistical distributions that are then sampled based on the parameters provided.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural_better.lua")

-- Generates wands with a base power of 100, 5 spell slots, and not unlimited.
generate_gun( 100, 5, false )
```