---
title: Experimental Wand 2 Configuration
category: data
---

# Experimental Wand 2 Configuration

This document details the configuration for an experimental wand entity in Noita, focusing on its procedural generation and item properties.

## Wand Properties

This section outlines the core attributes of the wand, which are randomized within defined ranges during generation.

### Key Attributes:

*   **`name`**: A table of possible names for the wand. The generated wand will randomly select one from this list.
    *   Example: `{"Colour wand"}`
*   **`deck_capacity`**: The maximum number of spells the wand can hold.
    *   Value: `10`
*   **`actions_per_round`**: The number of spells that can be cast per wand action.
    *   Value: `1`
*   **`reload_time`**: The time it takes for the wand to reload after casting spells. This is a range, and a random value within it will be chosen.
    *   Range: `{40, 60}`
*   **`shuffle_deck_when_empty`**: Determines if the wand's deck is shuffled when it runs out of spells.
    *   Value: `0` (False)
*   **`fire_rate_wait`**: The delay between consecutive spell casts.
    *   Value: `20`
*   **`spread_degrees`**: The angular spread of the spells cast by the wand.
    *   Value: `0`
*   **`speed_multiplier`**: A multiplier affecting the speed of the projectiles.
    *   Value: `1.0`
*   **`mana_charge_speed`**: The speed at which the wand's mana regenerates. This is a range.
    *   Range: `{100, 200}`
*   **`mana_max`**: The maximum mana capacity of the wand. This is a range.
    *   Range: `{500, 600}`

## Spell Configuration

The wand is configured to cast a specific sequence of spells, with some spells being randomly chosen from a set of colors.

### Spell Actions:

The `AddGunAction` function is used to define the spells cast by the wand. The following spells are added:

1.  A random color spell (from `COLOUR_RED`, `COLOUR_PURPLE`, `COLOUR_ORANGE`, `COLOUR_BLUE`, `COLOUR_YELLOW`, `COLOUR_GREEN`).
2.  `SPITTER_TIER_3`
3.  A random color spell.
4.  `SPITTER_TIER_3`
5.  A random color spell.
6.  `SPITTER_TIER_3`
7.  `COLOUR_INVIS`
8.  `SPITTER_TIER_3`
9.  `COLOUR_RAINBOW`
10. `SPITTER_TIER_3`

## Item Component

This section details the properties related to how the wand appears and behaves as an item in the game.

### Key Attributes:

*   **`item_name`**: The internal identifier for the item, used for localization.
    *   Value: `"$item_wand_experimental_2"`
*   **`always_use_item_name_in_ui`**: A flag to ensure the item's name is always displayed in the UI, even if it's a common item.
    *   Value: `true`

## Helper Functions

The script utilizes several utility functions for random selection and range generation.

### `get_random_from(target)`

*   **Description**: Selects and returns a single random element from a given table as a string.
*   **Parameters**:
    *   `target` (table): The table from which to select a random element.
*   **Returns**:
    *   (string): A randomly selected element from the `target` table.

### `get_multiple_random_from(target, amount_)`

*   **Description**: Selects and returns a specified number of random elements from a given table as strings.
*   **Parameters**:
    *   `target` (table): The table from which to select random elements.
    *   `amount_` (number, optional): The number of random elements to select. Defaults to 1.
*   **Returns**:
    *   (table): A table containing the randomly selected elements.

### `get_random_between_range(target)`

*   **Description**: Generates a random integer between the minimum and maximum values specified in a two-element table.
*   **Parameters**:
    *   `target` (table): A table containing two numbers: `[min_value, max_value]`.
*   **Returns**:
    *   (number): A random integer within the specified range (inclusive).