---
title: Item Spawn Lists
category: scripts
---

# Item Spawn Lists

This document details the structure and usage of item spawn lists in Noita, which define how various items are generated in the game world. These lists are crucial for modders looking to customize item drops, modify existing spawn behaviors, or introduce new item generation mechanics.

## Core Concepts

Spawn lists are Lua tables that dictate which entities can be spawned and under what conditions. They are typically referenced by a unique name (e.g., `potion_spawnlist`) and contain a set of "spawns" that are chosen based on a random value.

### Key Attributes of a Spawn List:

*   **`rnd_min`**: The minimum value for the random number generator used to select an item from this list.
*   **`rnd_max`**: The maximum value for the random number generator.
*   **`spawns`**: A table containing individual spawn definitions.

### Key Attributes of a Spawn Definition:

Each entry within the `spawns` table defines a potential entity to spawn.

*   **`value_min`**: The minimum random value required for this spawn to be considered.
*   **`value_max`**: The maximum random value required for this spawn to be considered.
*   **`load_entity`**: The direct path to an entity's XML file to be loaded.
*   **`load_entity_func`**: A Lua function that is executed to load the entity. This allows for more complex spawning logic, including conditional spawning based on game state or random variations.
*   **`load_entity_from_list`**: Allows one spawn list to trigger the spawning process from another spawn list.
*   **`offset_x` / `offset_y`**: Adjusts the spawn position relative to the base coordinates.
*   **`spawn_requires_flag`**: A game flag that must be present for this spawn to be considered.

## Example Spawn Lists

### `potion_spawnlist`

This is a general spawn list for potions and other common pickups.

| `value_min` | `value_max` | Entity/Logic