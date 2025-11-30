---
title: Procedural Gun Generation Parameters
category: scripts
---

# Procedural Gun Generation Parameters

This document outlines the parameters and logic used in Noita for procedurally generating guns, focusing on the `gun_procedural_better.lua` script. It details the probability distributions for various gun attributes and the functions that apply these attributes during generation.

## Core Gun Attributes and Distributions

The `gun_probs` table defines the probability distributions for key gun characteristics. Each attribute has a `min`, `max`, `mean`, and `sharpness` value that influences how it's randomly generated.

### `deck_capacity`

Determines how many spells can be held in the wand's deck.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "deck_capacity"                           |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

### `reload_time`

The time it takes for the wand to reload after firing all its spells.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "reload_time"                             |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

### `fire_rate_wait`

The delay between firing spells in a wand. Lower values mean faster firing.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "fire_rate_wait"                          |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

### `spread_degrees`

The angular spread of projectiles fired by the wand.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "spread_degrees"                          |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

### `speed_multiplier`

Affects the projectile speed.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "speed_multiplier"                        |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

### `actions_per_round`

The number of spells that can be cast per wand "round" (before a reload).

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `name`      | "actions_per_round"                       |
| `prob`      | Probability of this distribution being chosen (1 for this entry) |
| `min`       | Minimum possible value                    |
| `max`       | Maximum possible value                    |
| `mean`      | Average value                             |
| `sharpness` | Controls the distribution's peakiness     |

## Helper Functions

Several utility functions are used to manage and apply these parameters.

### `init_total_prob(value)`

Calculates and sets the `total_prob` for a given probability table.

### `init_gun_probs()`

Initializes the `total_prob` for all entries in the `gun_probs` table.

### `get_gun_probs(what)`

Retrieves a random distribution entry from `gun_probs` based on the specified attribute name (`what`).

### `apply_random_variable(t_gun, variable)`

Applies a randomly selected value for a given `variable` to the `t_gun` table, adjusting the gun's `cost` accordingly. This function contains specific logic for how each variable affects cost and its own min/max bounds based on the current cost.

### `WandDiff(gun, wand)`

Calculates a "difference score" between a generated `gun`'s properties and a predefined `wand`'s properties. This is used to find the closest matching wand sprite and grip.

### `GetWand(gun)`

Finds the most suitable predefined wand from the `wands` table that best matches the generated `gun`'s properties using `WandDiff`.

## Gun Generation Logic

The `generate_gun(cost, level, force_unshuffle)` function orchestrates the procedural generation of a gun.

### Key Steps:

1.  **Initialization**: Sets up the gun's base properties, including `cost`, `mana_charge_speed`, `mana_max`, and `force_unshuffle` based on `level` and random chance.
2.  **Variable Application**: Randomly shuffles and applies attributes from `variables_01`, `variables_02`, and `variables_03` using `apply_random_variable`.
3.  **Cost-Based Adjustments**: Further modifies `deck_capacity` based on remaining `cost`.
4.  **Sprite Selection**: Determines the appropriate wand sprite using `GetWand`.
5.  **Spell Addition**: Adds spells to the gun's deck, with logic for `ACTION_TYPE_PROJECTILE`, `ACTION_TYPE_MODIFIER`, and `ACTION_TYPE_DRAW_MANY` based on `deck_capacity`, `level`, and randomness.
6.  **Component Updates**: Sets the final gun properties on the entity's `AbilityComponent`.

### Notable Parameters within `generate_gun`:

*   **`cost`**: The primary driver for gun complexity and power.
*   **`level`**: Influences base mana, mana charge speed, and the likelihood of rarer attributes.
*   **`force_unshuffle`**: A flag that can force the wand to not shuffle its deck when empty.
*   **`is_rare`**: A flag for generating rarer, more powerful guns with increased cost and visual effects.
*   **`card_count`**: Determines how many spells are added to the gun's deck.
*   **`random_bullets`**: A flag that influences the addition of random projectile spells.

This script provides a robust framework for creating a wide variety of wands with distinct properties and playstyles.