---
title: Starting Potion Configuration
category: scripts/items
---

# Starting Potion Configuration

This script defines the initial material for starting potions in Noita. The material is determined by a series of random checks, influenced by factors like the number of player deaths and specific in-game dates.

## Key Attributes and Logic

### `potion_a_materials()` Function

This function dictates the possible materials a starting potion can contain. The selection process involves multiple random rolls with varying probabilities.

*   **Base Materials (65% chance):**
    *   `mud` (10% of this 65%)
    *   `water_swamp` (10% of this 65%)
    *   `water_salt` (10% of this 65%)
    *   `swamp` (10% of this 65%)
    *   `snow` (10% of this 65%)
    *   `water` (remaining 50% of this 65%)

*   **Blood (5% chance):**
    *   `blood`

*   **Special Magic Liquids (29% chance):**
    *   A random selection from: `acid`, `magic_liquid_polymorph`, `magic_liquid_random_polymorph`, `magic_liquid_berserk`, `magic_liquid_charm`, `magic_liquid_movement_faster`.

*   **Rare Materials (1 in 100,000 chance):**
    *   `urine` (if random roll is 666)
    *   `gold` (if random roll is 79)
    *   A random selection from: `slime`, `gunpowder_unstable` (for all other rare rolls).

### `init(entity_id)` Function

This is the main initialization function for the starting potion entity.

1.  **Seed Generation:** Sets a random seed based on the potion's X and Y coordinates. This ensures that potions at the same location will always have the same material.
2.  **Default Material:** Initializes `potion_material` to `"water"`.
3.  **Death Count Influence:** If the player has died one or more times (`StatsGlobalGetValue("death_count") >= 1`), the `potion_a_materials()` function is called to determine the potion's material.
4.  **Date-Specific Material:**
    *   On May 1st or April 30th, there's a 20% chance the potion material will be set to `"sima"`.
5.  **Final Initialization:** Calls `init_potion(entity_id, potion_material)` to apply the determined material to the potion entity.

### Note on Overrides

A comment indicates that a mod named `nightmare potion.lua` in the `mods/` directory can overwrite this script's functionality.