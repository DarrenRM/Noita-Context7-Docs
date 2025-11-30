---
title: Wand Unshuffle 02 - Procedural Wand Generation
category: guides
---

--[[
This script defines a procedural wand generation.
It utilizes the `generate_gun` function from `gun_procedural.lua`
to create a wand with specific parameters.
]]
```

---
title: Wand Unshuffle 02 - Procedural Wand Generation
category: scripts
---

# Wand Unshuffle 02 - Procedural Wand Generation

This script defines a procedural wand generation process for Noita. It leverages the `generate_gun` function to create wands with specific characteristics.

## Key Function

### `generate_gun( mana_charge, shuffle_weight, always_cast )`

This is the core function used to generate the wand. The parameters passed to it dictate the wand's properties.

*   **`mana_charge`**: An integer representing the base mana charge of the wand.
*   **`shuffle_weight`**: A number influencing how likely the wand is to shuffle its spells. Higher values mean more shuffling.
*   **`always_cast`**: A boolean. If `true`, the wand will always cast its spells without consuming mana.

## Script Logic

The script itself is very concise, primarily calling the `generate_gun` function with specific arguments.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

-- Generates a wand with:
-- - 40 base mana charge
-- - A shuffle weight of 2 (indicating a moderate tendency to shuffle)
-- - Spells will NOT always cast (false)
generate_gun( 40, 2, true )
```

## Parameters Used

In this specific instance of `generate_gun`:

*   **`mana_charge`**: `40`
*   **`shuffle_weight`**: `2`
*   **`always_cast`**: `true`

This configuration results in a wand that has a decent mana pool, a moderate chance of shuffling its spell order, and will cast its spells without consuming mana.