---
title: Utility Box Item Script
category: scripts
---

# Utility Box Item Script

This script defines the behavior for the "Utility Box" item in Noita, primarily focusing on its functionality when opened or picked up. It handles the spawning of random rewards, including utility cards, spells, bombs, and other miscellaneous items.

## Core Functions

### `make_random_utility_card(x, y)`

This function is responsible for creating a random utility card at the specified coordinates. It iterates through a list of available actions, checking for specific conditions like `ACTION_TYPE_UTILITY` or `ACTION_TYPE_MODIFIER`, and whether the player has met any required persistent flags. It ensures that items with a `spawn_probability` of "0" are not selected.

### `drop_random_reward(x, y, entity_id, rand_x, rand_y, set_rnd_)`

This is the main function for determining and spawning rewards. It uses a weighted random system to decide which item to drop.

**Key Reward Types and Probabilities:**

*   **Bomb (2%):** Spawns a small bomb.
*   **Spell Refresh (3%):** Spawns a spell refresh item. With a 2% chance, it might spawn a shaman wind illusion instead.
*   **Misc Items (6%):** A selection of items including:
    *   Safe Haven
    *   Moon
    *   Thunderstone
    *   Evil Eye
    *   Brimstone
    *   Runestones (randomly selected from a predefined list)
    *   Dice (physics_greed_die or physics_die based on game flags)
    *   Orbs (physics_gold_orb_greed or physics_gold_orb based on game flags)
*   **Random Cards (86%):** Spawns multiple utility cards. The number of cards spawned can vary from 2 to 6 based on a random roll.
*   **Exploding "Dice" (2%):** Triggers `drop_random_reward` to be called 2 more times.
*   **Exploding "Dice" (1%):** Triggers `drop_random_reward` to be called 3 more times.

The function also handles applying transformations and setting `next_frame_pickable` for auto-pickup items to prevent them from being instantly collected.

### `on_open(entity_item)`

This function is called when the utility box is opened. It retrieves the entity's position, sets a random seed based on its coordinates, and then calls `drop_random_reward` to spawn the loot. It also spawns a visual effect indicating whether a good or bad item was dropped.

### `item_pickup(entity_item, entity_who_picked, name)`

This function is triggered when the player picks up the utility box. It logs a message, calls `on_open` to spawn rewards, and then destroys the utility box entity.

### `physics_body_modified(is_destroyed)`

This function is called when the utility box's physics body is modified (e.g., broken). It also triggers `on_open` to spawn rewards and then destroys the entity.

## Key Attributes and Elements

*   **`actions` table:** This global table (defined elsewhere) contains all available actions that can be spawned as utility cards.
*   **`ACTION_TYPE_UTILITY` and `ACTION_TYPE_MODIFIER`:** Constants used to filter which types of actions can be spawned as utility cards.
*   **`spawn_requires_flag`:** An attribute on actions that specifies a persistent flag the player must possess to spawn that action.
*   **`spawn_probability`:** An attribute on actions that can be used to control their spawn rate.
*   **`PositionSeedComponent`:** Used to determine the random seed for reward generation based on the entity's position.
*   **`ItemComponent`:** Used to manage item properties like `auto_pickup` and `next_frame_pickable`.
*   **`GameGetFrameNum()`:** Returns the current game frame number, used for timing `next_frame_pickable`.
*   **`EntityLoad()`:** Spawns an entity at a given position.
*   **`EntityApplyTransform()`:** Applies a transformation to an entity.
*   **`EntityKill()`:** Destroys an entity.
*   **`HasFlagPersistent()` and `GameHasFlagRun()`:** Functions to check for persistent and run-specific game flags.
*   **`Random()`:** Generates a random number within a specified range.
*   **`SetRandomSeed()`:** Sets the seed for the random number generator.

This script provides a robust system for generating varied and potentially powerful rewards when interacting with the Utility Box.