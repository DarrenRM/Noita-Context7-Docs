---
title: Procedural Gun Generation Data
category: scripts
---

# Procedural Gun Generation Data

This file defines the parameters and logic for procedurally generating wands (guns) in Noita. It outlines various attributes that can be randomized, their probability distributions, and how they influence the final generated wand.

## Core Concepts

The generation process relies on a `gun_probs` table, which stores probability distributions for different wand attributes. These distributions are used to randomly select values within defined ranges, influenced by factors like cost and player level.

## Key Attributes and Distributions

The `gun_probs` table contains definitions for several key wand attributes. Each attribute is a table containing multiple entries, each with a `prob` (probability of selection) and a range (`min`, `max`, `mean`, `sharpness`) for its value.

### `deck_capacity`

Determines how many spells can be held in the wand's deck.

| Prob   | Min | Max | Mean | Sharpness | Notes                               |
| :----- | :-- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | 3   | 10  | 6    | 2         | Normal distribution                 |
| 0.1    | 2   | 7   | 4    | 4         | Unshuffled, higher unshuffle prob   |
| 0.05   | 1   | 5   | 3    | 4         | Unshuffled tiny, higher unshuffle prob |
| 0.15   | 5   | 11  | 8    | 2         | Machine gun                         |
| 0.12   | 2   | 20  | 8    | 4         | Everything goes                     |
| 0.15   | 3   | 12  | 6    | 6         | Shotgun, higher draw many prob      |
| 1      | 1   | 20  | 6    | 0         | Linear distribution (crazyw)        |

### `reload_time`

The time it takes for the wand to reload after firing all its spells.

| Prob   | Min | Max | Mean | Sharpness | Notes                               |
| :----- | :-- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | 5   | 60  | 30   | 2         | Normal distribution                 |
| 0.5    | 1   | 100 | 40   | 2         | Wider range                         |
| 0.02   | 1   | 100 | 40   | 0         | Linear distribution                 |
| 0.35   | 1   | 240 | 40   | 0         | Linear distribution (crazy), adds unshuffle prob |

### `fire_rate_wait`

The delay between firing spells. Lower values mean faster firing.

| Prob   | Min  | Max | Mean | Sharpness | Notes                               |
| :----- | :--- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | 1    | 30  | 5    | 2         | Machine gun                         |
| 0.1    | 1    | 50  | 15   | 3         | Shotgun                             |
| 0.1    | -15  | 15  | 0    | 3         | Submachine gun                      |
| 0.45   | 0    | 35  | 12   | 0         | Linear distribution (anything goes) |

### `spread_degrees`

The angular spread of projectiles fired by the wand.

| Prob   | Min  | Max | Mean | Sharpness | Notes                               |
| :----- | :--- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | -5   | 10  | 0    | 3         | Pistol-like spread                  |
| 0.1    | -35  | 35  | 0    | 0         | Linear distribution (crazy)         |

### `speed_multiplier`

Affects the projectile speed.

| Prob   | Min | Max | Mean | Sharpness | Notes                               |
| :----- | :-- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | 0.8 | 1.2 | 1    | 6         | Standard distribution               |
| 0.05   | 1   | 2   | 1.1  | 3         | Faster bullets                      |
| 0.05   | 0.5 | 1   | 0.9  | 3         | Slow bullets                        |
| 1      | 0.8 | 1.2 | 1    | 0         | Linear distribution                 |
| 0.001  | 1   | 10  | 5    | 2         | Easter egg                          |

### `actions_per_round`

The number of actions (spells) the wand can perform per firing cycle.

| Prob   | Min | Max | Mean | Sharpness | Notes                               |
| :----- | :-- | :-- | :--- | :-------- | :---------------------------------- |
| 1      | 1   | 3   | 1    | 3         | Standard distribution               |
| 0.2    | 2   | 4   | 2    | 8         | Shotgun                             |
| 0.05   | 1   | 5   | 2    | 2         | Crazy                               |
| 1      | 1   | 5   | 2    | 0         | Linear distribution                 |

## Helper Functions

The script includes several utility functions for generating and manipulating wand properties:

*   `init_total_prob(value)`: Calculates the total probability for a given attribute's distribution.
*   `init_gun_probs()`: Initializes the total probabilities for all attributes in `gun_probs`.
*   `get_gun_probs(what)`: Retrieves a specific probability distribution entry for a given attribute.
*   `apply_random_variable(t_gun, variable)`: Applies a randomly selected value for a given wand attribute, adjusting the wand's cost accordingly.
*   `WandDiff(gun, wand)`: Calculates a "difference" score between a generated gun's properties and predefined wand archetypes.
*   `GetWand(gun)`: Selects a predefined wand archetype that best matches the generated gun's properties.
*   `get_gun_data(cost, level, force_unshuffle)`: The core function for generating the raw data of a wand based on cost, level, and other factors.
*   `wand_add_random_cards(gun, entity_id, level)`: Adds random spells (cards) to the generated wand.
*   `make_wand_from_gun_data(gun, entity_id, level)`: Configures the entity's components with the generated wand data.
*   `generate_gun(cost, level, force_unshuffle)`: The main entry point for creating a new procedural wand.

## Internal Data Structures

*   `gun_probs`: A table containing probability distributions for wand attributes.
*   `gun_names`: A list of potential names for generated wands.
*   `wands`: (Assumed to be defined elsewhere) A table containing predefined wand archetypes used for matching generated wands.

This file serves as the blueprint for how Noita procedurally generates wands, offering a complex interplay of probabilities and attribute dependencies.