---
title: Daily Wand Generation Script
category: scripts
---

# Daily Wand Generation Script

This script defines parameters for generating a daily wand in Noita. It leverages the `generate_daily_wand` function from `wand_daily.lua` to create a unique wand configuration for each day.

## Key Parameters

The `generate_daily_wand` function takes the following primary arguments:

*   **`wand_level`**: An integer representing the overall power level or tier of the wand. Higher values generally lead to more potent wands.
*   **`num_spells`**: An integer specifying the number of spells to be included in the generated wand.
*   **`guaranteed_unique`**: A boolean value. If `true`, the wand is guaranteed to have at least one unique spell. If `false`, this guarantee is not present.

## Example Usage

The provided script demonstrates a specific daily wand generation:

```lua
dofile_once("data/scripts/gun/procedural/wand_daily.lua")

-- Generates a daily wand with level 120, 6 spells, and no guaranteed unique spell.
generate_daily_wand( 120, 6, false )

-- The following line is commented out and represents an alternative generation for a regular gun, not a daily wand.
-- generate_gun( 40, 2, false )
```

## AI Modding Considerations

For AI-assisted modding, understanding these parameters is crucial for:

*   **Procedural Generation Control**: Modders can create their own functions that call `generate_daily_wand` with custom arguments to influence the types and power of daily wands generated.
*   **Balancing**: Adjusting `wand_level` and `num_spells` allows for fine-tuning the difficulty and reward structure of daily challenges.
*   **Unique Spell Integration**: The `guaranteed_unique` parameter can be used to ensure that daily wands offer players opportunities to discover new or rare spell combinations.
*   **Custom Wand Logic**: By examining `wand_daily.lua` (which this script depends on), modders can understand the underlying logic for spell selection and wand property assignment, enabling more complex modifications.