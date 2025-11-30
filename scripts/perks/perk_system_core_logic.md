---
title: Perk System Core Logic
category: scripts/perks
---

# Perk System Core Logic

This document outlines the core logic and functions related to the perk system in Noita, focusing on how perks are managed, spawned, and picked up.

## Core Functionality

### `perk_is_stackable(perk_data)`

Determines if a perk can be picked up multiple times.

-   **Returns:**
    -   `boolean`: `true` if the perk is stackable, `false` otherwise.
    -   `boolean`: `true` if the perk is stackable but rare (appears less frequently).

### `perk_get_spawn_order(ignore_these)`

Generates a deterministic, shuffled list of perks available for the current world seed. This function ensures that the perk order is consistent within a run.

-   **Parameters:**
    -   `ignore_these` (optional table): A list of perk IDs to exclude from the spawn order.
-   **Key Logic:**
    1.  **Deck Creation:** Builds a "deck" of perks, including multiple instances of stackable perks based on their rarity and maximum pool count.
    2.  **Shuffling:** Randomly shuffles the perk deck.
    3.  **Duplicate Removal:** Removes duplicate stackable perks that appear too close to each other in the shuffled deck to ensure variety.
    4.  **Picked Perk Filtering:** Iterates through the deck and marks perks as empty (`""`) if they have been picked up and cannot be stacked further.

### `perk_pickup(entity_item, entity_who_picked, item_name, do_cosmetic_fx, kill_other_perks, no_perk_entity_)`

Handles the logic when a player picks up a perk.

-   **Parameters:**
    -   `entity_item`: The entity representing the perk item being picked up.
    -   `entity_who_picked`: The entity of the player picking up the perk.
    -   `item_name`: The internal name of the perk.
    -   `do_cosmetic_fx` (boolean): Whether to play visual effects and messages.
    -   `kill_other_perks` (boolean): Whether to remove other visible perks.
    -   `no_perk_entity_` (boolean): Internal flag.
-   **Key Actions:**
    1.  **Perk Data Retrieval:** Fetches the perk's data based on its ID.
    2.  **Pickup Tracking:** Increments a global counter for how many times this perk has been picked up in the current run.
    3.  **Flag Application:** Adds relevant game flags to mark the perk as acquired.
    4.  **Effect Application:** Applies associated game effects, particle effects, and UI elements.
    5.  **Perk Removal Logic:** If specified, removes other perks or disables perk rerolling machines.
    6.  **Cosmetic FX:** Triggers visual effects and important game messages.
    7.  **Entity Cleanup:** Destroys the perk item entity.

### `perk_spawn(x, y, perk_id, dont_remove_other_perks_)`

Spawns a specific perk at given coordinates.

-   **Parameters:**
    -   `x`, `y`: Coordinates for spawning.
    -   `perk_id`: The internal ID of the perk to spawn.
    -   `dont_remove_other_perks_` (boolean): If `true`, this perk will not trigger the removal of other perks when picked up.
-   **Key Actions:**
    1.  **Perk Data Lookup:** Retrieves perk data.
    2.  **Entity Creation:** Creates a `perk.xml` entity at the specified location.
    3.  **Component Addition:** Adds necessary components like `SpriteComponent`, `UIInfoComponent`, `ItemComponent`, and `VariableStorageComponent` to define the perk's appearance, behavior, and ID.

### `perk_spawn_random(x, y, dont_remove_others_)`

Spawns a single random perk at given coordinates, using the `perk_get_spawn_order` to determine the next available perk.

-   **Parameters:**
    -   `x`, `y`: Coordinates for spawning.
    -   `dont_remove_others_` (boolean): If `true`, this perk will not trigger the removal of other perks when picked up.
-   **Key Logic:**
    -   Retrieves the next perk from the globally managed spawn order.
    -   Updates the global index for the next perk.
    -   Calls `perk_spawn` to create the perk entity.

### `perk_spawn_many(x, y, dont_remove_others_, ignore_these_)`

Spawns multiple perks, typically used in specific game areas like the Temple.

-   **Parameters:**
    -   `x`, `y`: Base coordinates for spawning.
    -   `dont_remove_others_` (boolean): If `true`, spawned perks will not trigger the removal of other perks when picked up.
    -   `ignore_these_` (optional table): A list of perk IDs to exclude from this specific spawn batch.
-   **Key Logic:**
    -   Determines the number of perks to spawn based on a global setting (`TEMPLE_PERK_COUNT`).
    -   Calculates spawn positions to arrange perks in a line.
    -   Uses `perk_get_spawn_order` to select perks and manages a global index (`TEMPLE_NEXT_PERK_INDEX`) for sequential spawning.
    -   Calls `perk_spawn` for each selected perk.

## Helper Functions

### `get_perk_flag_name(perk_id)`

Constructs the internal flag name for a given perk ID (e.g., `PERK_FAST_TRAVEL`).

### `get_perk_picked_flag_name(perk_id)`

Constructs the flag name used for tracking perk pickup counts (e.g., `PERK_FAST_TRAVEL_PICKUP_COUNT`).

### `get_perk_with_id(perk_list, perk_id)`

Searches the global `perk_list` for a perk matching the given ID.

### `shuffle_table(t)`

A utility function to randomly shuffle the elements of a table in place.

### `table_contains(table, element)`

Checks if a given element exists within a table.

## Debugging and Utility Functions

### `DEBUG_PERKS()`

A function for debugging the perk system. It can be used to:
-   Print the stackable status of all perks.
-   Verify if all defined perks are included in the spawn order.
-   Analyze the distribution of stackable vs. non-stackable perks.

### `IMPL_remove_all_perks(player_id)`

Removes all applied perks from a specific player entity. This involves:
-   Removing game flags and resetting pickup counts.
-   Disabling associated game effects and components.
-   Killing perk-related entities attached to the player.
-   Resetting various player status variables (rattiness, fungal level, etc.).

### `remove_all_perks()`

A wrapper function to call `IMPL_remove_all_perks` for the primary player.

### `create_all_player_perks(x, y)`

Spawns all perks that the player has acquired during the current run at specified coordinates, often used for visual representation or special game modes. It arranges them in an arc.