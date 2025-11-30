---
title: Wand Debugging and Generation Script
category: scripts
---

# Wand Debugging and Generation Script

This script provides functionality for debugging and generating Noita wands based on specific parameters. It analyzes existing wand data to determine attribute ranges and offers a function to find the closest matching wand from the game's predefined list.

## Core Functionality

The script primarily focuses on two key areas:

1.  **Attribute Range Analysis:** It iterates through all available wands to calculate the minimum and maximum values for several key wand attributes. This helps understand the spectrum of values present in the game.
2.  **Wand Matching:** It provides a function (`GetWand`) that takes a set of desired wand attributes and finds the predefined wand that most closely matches these parameters.

## Key Wand Attributes Analyzed

The script focuses on the following attributes when analyzing and matching wands:

*   **`fire_rate_wait`**: The delay between shots.
*   **`actions_per_round`**: The number of spells cast per wand action.
*   **`shuffle_deck_when_empty`**: Whether the wand shuffles its deck when empty.
*   **`deck_capacity`**: The maximum number of spells the wand can hold.
*   **`spread_degrees`**: The spread of projectiles fired by the wand.
*   **`reload_time`**: The time it takes for the wand to reload.

## Functions

### `Min(x, y)`

A helper function to return the smaller of two numbers.

### `Max(x, y)`

A helper function to return the larger of two numbers.

### `WandDiff(gun, wand)`

Calculates a "difference score" between a target `gun` (represented by its attributes) and a predefined `wand`. The score is the sum of the absolute differences of each attribute. A lower score indicates a closer match.

### `GetWandDebug(fire_rate_wait, actions_per_round, shuffle_deck_when_empty, deck_capacity, spread_degrees, reload_time)`

This function is designed for debugging. It takes raw attribute values and attempts to find the closest matching wand from the `wands` table. It uses `WandDiff` to score potential matches.

### `clamp(val, lower, upper)`

Ensures a given value `val` stays within a specified `lower` and `upper` bound. It also handles cases where `lower` and `upper` might be provided in the wrong order.

### `GetWand(gun)`

This is the primary function for generating or finding a wand. It takes a `gun` table containing desired attributes, converts these attributes into a "wand space" (a normalized representation used internally by the game's wand system), and then uses `WandDiff` to find the closest matching predefined wand.

The conversion to "wand space" involves specific scaling and clamping for each attribute, as indicated by the commented-out sections in the source.

## Attribute Ranges

The script calculates and prints the minimum and maximum values found for each key attribute across all wands in the game. This provides a useful overview of the possible ranges for modding purposes.

```lua
-- Example output from the script:
-- fire_rate_wait:  0.03333333333333333  -  1.5
-- actions_per_round:  1  -  10
-- shuffle_deck_when_empty:  0  -  1
-- deck_capacity:  3  -  20
-- spread_degrees:  -35  -  35
-- reload_time:  5  -  100
```

## Example Usage

The script includes an example of how to define a `gun` with specific attributes and then use `GetWand` to find the closest matching wand.

```lua
local gun = {}
gun["fire_rate_wait"] = 15
gun["actions_per_round"] = 1
gun["shuffle_deck_when_empty"] = 1
gun["deck_capacity"] = 7.36
gun["spread_degrees"] = 1
gun["reload_time"] = 39

local bwand = GetWand( gun )
print( "bwand: ", bwand.fire_rate_wait, bwand.actions_per_round, bwand.shuffle_deck_when_empty, bwand.deck_capacity, bwand.spread_degrees, bwand.reload_time )
```