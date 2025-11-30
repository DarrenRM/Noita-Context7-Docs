---
title: Chest Random Super
category: scripts
---

# Chest Random Super

This script defines the behavior for a "super" random chest in Noita, responsible for dispensing a variety of items. It handles the logic for determining what items are dropped, their quantities, and applying necessary transformations.

## Core Functionality

The primary function `drop_random_reward` dictates the item generation process. It uses a weighted random system to select from different categories of items, including potions, gold, hearts, and wands. The `on_open` function is triggered when the chest is interacted with, initiating the reward drop.

## Key Attributes and Elements

### `drop_random_reward(x, y, entity_id, rand_x, rand_y, set_rnd)`

This function orchestrates the dropping of random rewards.

*   **`x`, `y`**: Coordinates where the chest is located.
*   **`entity_id`**: The ID of the chest entity.
*   **`rand_x`, `rand_y`**: Random coordinates used for entity placement.
*   **`set_rnd`**: A boolean flag to control whether a new random seed is set.

### Item Drop Logic (within `drop_random_reward`)

The script uses a series of `if/elseif` statements based on a random number (`rnd`) to determine the type and quantity of items dropped.

| `rnd` Range | Item Category                 | Details