---
title: Shop Item Generation
category: scripts
---

# Shop Item Generation

This script defines functions for generating shop items and wands in Noita, determining their appearance, cost, and behavior.

## `generate_shop_item(x, y, cheap_item, biomeid_, is_stealable)`

This function creates a generic shop item.

### Key Parameters:

*   `x`, `y`: World coordinates for item placement.
*   `cheap_item`: Boolean, if true, the item will have a reduced price.
*   `biomeid_`: Optional, forces a specific biome ID for cost calculation.
*   `is_stealable`: Boolean, determines if the item can be stolen.

### Core Logic:

1.  **Biome Determination:** Calculates the biome ID based on the `y` coordinate, with a fallback for deeper levels.
2.  **Item Selection:** Randomly selects an item from the `actions` table (presumably defined elsewhere, likely in `gun/gun_actions.lua`).
3.  **Cost Calculation:**
    *   Base cost is derived from the item's `price` attribute and the biome ID.
    *   The biome ID is squared for price scaling.
    *   Costs are rounded to the nearest 10.
    *   Deep biomes (>= 10) significantly increase the cost.
    *   `cheap_item` halves the cost.
4.  **Entity Creation:**
    *   Creates an `ItemActionEntity` for the selected item.
    *   If `cheap_item` is true, a "sale indicator" entity is spawned.
5.  **Component Addition:**
    *   **`SpriteComponent`**: Displays the item's cost as text.
    *   **`ItemCostComponent`**: Sets the item's cost and stealable status.
    *   **`LuaComponent`**: Links to `shop_effect.lua` for handling item pickup logic.

### Biome ID Mapping:

The script uses a table to map vertical chunks of the world to biome IDs.

| Chunk Index | Biome ID |
| :---------- | :------- |
| 1-3         | 0        |
| 4-6         | 1        |
| 7-12        | 2        |
| 13-16       | 3        |
| 17-20       | 4        |
| 21-24       | 5        |
| 25-33       | 6        |

## `generate_shop_wand(x, y, cheap_item, biomeid_)`

This function creates a shop wand.

### Key Parameters:

*   `x`, `y`: World coordinates for wand placement.
*   `cheap_item`: Boolean, if true, the wand will have a reduced price.
*   `biomeid_`: Optional, forces a specific biome ID for cost calculation.

### Core Logic:

1.  **Biome Determination:** Similar to `generate_shop_item`, determines the biome ID based on `y` coordinate.
2.  **Wand Selection:** Randomly selects between a `wand_level_0` and `wand_unshuffle_0` variant, appending the biome ID.
3.  **Cost Calculation:**
    *   Wand cost is calculated based on a formula involving the biome ID, with a random variation.
    *   `cheap_item` halves the cost.
4.  **Entity Creation:**
    *   Loads the selected wand entity.
    *   If `cheap_item` is true, a "sale indicator" entity is spawned.
5.  **Component Addition:**
    *   **`SpriteComponent`**: Displays the wand's cost as text.
    *   **`ItemCostComponent`**: Sets the wand's cost and marks it as stealable.
    *   **`LuaComponent`**: Links to `shop_effect.lua` for handling item pickup logic.

### Biome ID Mapping:

Uses the same biome ID mapping as `generate_shop_item`.

---

**Note for Modders:** The `return eid` statement at the end of both functions is included for modding convenience, allowing direct access to the created entity ID.