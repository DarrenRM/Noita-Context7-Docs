---
title: Wand Level 02 Procedural Generation
category: scripts
---

# Wand Level 02 Procedural Generation

This script defines parameters for the procedural generation of wands found at level 02 in Noita. It utilizes the `gun_procedural.lua` library to create these wands.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`40`**: This likely represents a base "power" or "rarity" value for the wands generated at this level. Higher values generally lead to more potent or rarer wands.
*   **`2`**: This parameter could influence the number of spells or modifiers that can be attached to the generated wands. A value of `2` suggests a moderate complexity.
*   **`false`**: This boolean likely controls whether the generated wands are "limited" or "unlimited" in their spell capacity or charge usage. `false` suggests they are not limited in this specific way.

## Underlying Logic

The core of this generation is handled by the `gun_procedural.lua` script, which contains the comprehensive logic for creating procedural wands. This script (`wand_level_02.lua`) acts as a configuration file, specifying the desired characteristics for wands at this particular game stage.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

-- Generates wands for level 02 with specific parameters
generate_gun( 40, 2, false )
```