---
title: Perk Reroll Initialization
category: scripts
---

# Perk Reroll Initialization

This script handles the initialization and cost calculation for the perk reroll mechanic in Noita. It dynamically adjusts the cost of rerolling based on how many times the player has already rerolled perks.

## Key Components and Logic

### Cost Calculation

The core of this script is the dynamic calculation of the perk reroll cost.

*   **`perk_reroll_count`**: Retrieves the current number of perk rerolls from global game variables. Defaults to "0" if not found.
*   **`cost`**: Calculates the reroll cost using an exponential formula: `200 * math.pow(2, perk_reroll_count)`. This means the cost doubles with each subsequent reroll.

### Sprite Component Adjustment

This section focuses on visually updating the cost display in the game.

*   **`itemcost_comp`**: Gets the `ItemCostComponent` of the entity.
*   **`costsprite_comp`**: Retrieves the `SpriteComponent` associated with the shop cost.
*   **`offsetx`**: This variable is used to center the cost text. It's calculated based on the width of the cost string to ensure proper alignment.
    *   The script iterates through the digits of the `cost` string.
    *   It adds a fixed width (6 pixels) for most digits and a smaller width (3 pixels) for the digit "1" to approximate the visual width of each character.
    *   The final `offsetx` is half the total text width minus 0.5, effectively centering the text.

### Setting Component Values

*   **`ComponentSetValue( itemcost_comp, "cost", tostring(cost))`**: Updates the `ItemCostComponent` with the newly calculated `cost`, converted to a string.

## Summary of Key Attributes

| Attribute/Element        | Description                                                                                             |
| :----------------------- | :------------------------------------------------------------------------------------------------------ |
| `TEMPLE_PERK_REROLL_COUNT` | Global variable storing the number of times perks have been rerolled.                                   |
| `cost`                   | The calculated cost for the current perk reroll.                                                        |
| `math.pow(2, perk_reroll_count)` | Exponential factor used to increase the cost with each reroll.                                        |
| `SpriteComponent`        | Component responsible for rendering the visual elements, including the cost display.                    |
| `offset_x`               | Sprite component property adjusted to center the cost text.                                             |
| `ItemCostComponent`      | Component that stores and manages the cost of items or actions.                                         |

---