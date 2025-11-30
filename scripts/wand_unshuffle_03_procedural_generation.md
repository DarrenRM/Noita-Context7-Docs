---
title: Wand Unshuffle 03 Procedural Generation
category: scripts
---

# Wand Unshuffle 03 Procedural Generation

This script defines parameters for the procedural generation of a specific type of wand in Noita. It leverages the `gun_procedural.lua` library to create wands with defined characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`60`**: This likely represents a base **mana capacity** or a similar resource pool for the wand.
*   **`3`**: This could signify the **number of spell slots** available on the wand.
*   **`true`**: This boolean value might indicate whether the wand has a **randomized shuffle** behavior for its spells.

## Underlying Logic

The script relies on the `gun_procedural.lua` library for the actual generation process. This library handles the complex logic of combining spell effects, mana costs, projectile behaviors, and other attributes to create a functional wand. The parameters provided in `wand_unshuffle_03.lua` act as specific inputs to this broader generation system, tailoring the output to a particular wand archetype.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

-- Generates a wand with specific properties.
-- The exact meaning of each parameter is determined by the gun_procedural.lua script.
generate_gun( 60, 3, true )
```