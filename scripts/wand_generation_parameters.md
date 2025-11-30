---
title: Wand Generation Parameters
category: scripts
---

---

# Wand Generation Parameters

This document outlines the parameters and logic used in Noita for procedurally generating wands, focusing on the `wand_petri.lua` script. It details how various wand attributes are determined based on a cost system and probability distributions.

## Core Wand Attributes and Their Generation

The following attributes are key to defining a wand's behavior and are generated using probability tables and cost-based adjustments.

### `deck_capacity`

Determines how many spells can be held in the wand's deck.

| Name            | Probability | Min | Max | Mean | Sharpness | Notes                                                              |
| :-------------- | :---------- | :-- | :-- | :--- | :-------- | :----------------------------------------------------------------- |
| `normal`        | 1           | 3   | 10  | 6    | 2         | Standard capacity.                                                 |
| `unshuffled`    | 0.1         | 2   | 7   | 4    | 4         | Higher chance of drawing spells in order.                          |
| `unshuffled tiny` | 0.05        | 1   | 5   | 3    | 4         | Very small deck, high chance of ordered draws.                     |
| `machine gun`   | 0.15        | 5   | 11  | 8    | 2         | Larger deck, suitable for rapid firing.                            |
| `everything goes` | 0.12        | 2   | 20  | 8    | 4         | Wide range of capacities.                                          |
| `shotgun`       | 0.15        | 3   | 12  | 6    | 6         | Encourages drawing multiple spells.                                |
| `linear_crazyw` | 1           | 1   | 20  | 6    | 0         | Linear distribution across a wide range.                           |

### `reload_time`

The time it takes for the wand to reload after firing all its spells.

| Name    | Probability | Min | Max | Mean | Sharpness | Notes                                     |
| :------ | :---------- | :-- | :-- | :--- | :-------- | :---------------------------------------- |
| `normal`  | 1           | 5   | 60  | 30   | 2         | Standard reload times.                    |
| `normal`  | 0.5         | 1   | 100 | 40   | 2         | Another variation of normal reload.       |
| `linear`  | 0.02        | 1   | 100 | 40   | 0         | Linear distribution.                      |
| `linear_crazy` | 0.35        | 1   | 240 | 40   | 0         | Very wide linear distribution.            |

### `fire_rate_wait`

The delay between firing individual spells within a wand's action.

| Name                 | Probability | Min  | Max | Mean | Sharpness | Notes                                                              |
| :------------------- | :---------- | :--- | :-- | :--- | :-------- | :----------------------------------------------------------------- |
| `machine gun`        | 1           | 1    | 30  | 5    | 2         | Fast firing rate.                                                  |
| `shotgun`            | 0.1         | 1    | 50  | 15   | 3         | Slower firing rate, typical for shotguns.                          |
| `submachine gun`     | 0.1         | -15  | 15  | 0    | 3         | Can result in very rapid or slightly delayed firing.               |
| `linear_anything goes` | 0.45        | 0    | 35  | 12   | 0         | Wide linear distribution.                                          |

### `spread_degrees`

The angular spread of projectiles fired by the wand.

| Name         | Probability | Min  | Max | Mean | Sharpness | Notes                                                              |
| :----------- | :---------- | :--- | :-- | :--- | :-------- | :----------------------------------------------------------------- |
| `pistol`     | 1           | -5   | 10  | 0    | 3         | Tight spread, centered around zero.                                |
| `linear_crazy` | 0.1         | -35  | 35  | 0    | 0         | Very wide, linear spread.                                          |

### `speed_multiplier`

Affects the projectile speed.

| Name            | Probability | Min | Max | Mean | Sharpness | Notes                               |
| :-------------- | :---------- | :-- | :-- | :--- | :-------- | :---------------------------------- |
| `standard`      | 1           | 0.8 | 1.2 | 1    | 6         | Standard projectile speed.          |
| `faster bullets` | 0.05        | 1   | 2   | 1.1  | 3         | Increased projectile speed.         |
| `slow bullets`  | 0.05        | 0.5 | 1   | 0.9  | 3         | Decreased projectile speed.         |
| `linear`        | 1           | 0.8 | 1.2 | 1    | 0         | Linear distribution within standard range. |
| `easter_egg`    | 0.001       | 1   | 10  | 5    | 2         | Rare, very high speed multiplier.   |

### `actions_per_round`

The number of spell actions the wand can perform before reloading.

| Name     | Probability | Min | Max | Mean | Sharpness | Notes                                                              |
| :------- | :---------- | :-- | :-- | :--- | :-------- | :----------------------------------------------------------------- |
| `standard` | 1           | 1   | 3   | 1    | 3         | Standard actions per round.                                        |
| `shotgun`  | 0.2         | 2   | 4   | 2    | 8         | Higher actions per round, often associated with shotguns.          |
| `crazy`    | 0.05        | 1   | 5   | 2    | 2         | Wide range of actions.                                             |
| `linear`   | 1           | 1   | 5   | 2    | 0         | Linear distribution across the range.                              |

## Helper Functions

These functions are crucial for the procedural generation process.

### `init_total_prob(value)`

Calculates and stores the `total_prob` for a given probability table. This is used to normalize probabilities for random selection.

### `init_gun_probs()`

Initializes the `total_prob` for all probability tables defined in `gun_probs`.

### `get_gun_probs(what)`

Selects a random entry from a specified probability table (`what`) based on its defined probabilities.

### `apply_random_variable(t_gun, variable)`

Applies a randomly selected value for a given `variable` to the `t_gun` (wand data table). This function also adjusts the wand's `cost` based on the generated value and the variable's specific cost formula.

### `WandDiff(gun, wand)`

Calculates a "difference score" between a generated `gun`'s properties and a predefined `wand` template. This is used to find the closest matching wand sprite and grip.

### `GetWand(gun)`

Finds the most suitable predefined wand template (`wands` table) that best matches the generated `gun`'s properties using the `WandDiff` function.

## Generation Logic (`generate_gun`)

The `generate_gun` function orchestrates the entire wand generation process.

1.  **Initialization**: Sets up the wand's base properties, including `cost`, `level`, and a `force_unshuffle` flag.
2.  **Cost Adjustment**: The initial `cost` is adjusted based on `level` and a small random variation.
3.  **Base Wand Properties**: Initializes a `gun` table with default values for various attributes like `deck_capacity`, `reload_time`, `fire_rate_wait`, etc. It also sets initial values for `prob_unshuffle`, `prob_draw_many`, `mana_charge_speed`, and `mana_max`.
4.  **Rare Wand Check**: A small chance exists to make the wand "rare," significantly increasing its cost and applying a purple glow.
5.  **Variable Generation Order**: The generation of attributes is divided into three groups (`variables_01`, `variables_02`, `variables_03`) and applied in a specific, randomized order.
    *   `variables_01`: `reload_time`, `fire_rate_wait`, `spread_degrees`, `speed_multiplier`.
    *   `variables_02`: `deck_capacity`.
    *   `variables_03`: `shuffle_deck_when_empty`, `actions_per_round`.
6.  **`apply_random_variable` Calls**: Each variable is processed by `apply_random_variable`, which determines its value and adjusts the wand's `cost`.
7.  **Cost-to-Capacity Conversion**: Any remaining `cost` after generating other attributes can be converted into additional `deck_capacity`.
8.  **Sprite Assignment**: The `GetWand` function is called to select an appropriate wand sprite based on the generated properties.
9.  **Spell Card Assignment**: The function then procedurally adds spell cards to the wand's deck, prioritizing certain types of cards (e.g., `ACTION_TYPE_DRAW_MANY`) based on wand properties and random chance.
    *   `AddGunActionPermanent` is used for spells that are permanently attached.
    *   `AddGunAction` is used for spells added to the wand's deck.
10. **Finalization**: The wand's UI name, sprite, and other component values are set.