---
title: Lava Lake Pit Biome Configuration
category: scripts/biome
---

---

# Lava Lake Pit Biome Configuration

This document details the configuration for the Lava Lake Pit biome in Noita, focusing on its spawning mechanics and visual elements.

## Core Biome Functions

The Lava Lake Pit biome utilizes a set of default functions for its initialization and entity spawning.

### Initialization (`init`)

The `init` function is responsible for loading the visual representation of the biome. It dynamically selects between two different pixel scene files based on the Y-coordinate of the spawn area.

*   **`init(x, y, w, h)`**:
    *   If `y` is between 2000 and 2400, it loads `data/biome_impl/lavalake_pit_cracked.png`.
    *   Otherwise, it loads the default `data/biome_impl/lavalake_pit.png`.

### Meta-Portal Spawning (`spawn_metportal`)

This function handles the placement of meta-portals within the biome.

*   **`spawn_metportal(x, y)`**:
    *   Loads the `data/entities/buildings/teleport_lavalake.xml` entity at the specified coordinates.

## Entity Spawning

The biome defines specific functions for spawning various entities, though many are left unimplemented or are placeholders.

### Item Spawning (`g_items` and `spawn_wands`)

The `g_items` table defines the probabilities and types of items that can spawn. `spawn_wands` is the function that utilizes this table.

*   **`g_items` Table**:
    *   `total_prob`: The total probability for all items in the table.
    *   **Item Entry Example**:
        ```lua
        {
            prob      = 5,  -- Probability of this item spawning
            min_count = 1,  -- Minimum number of this item to spawn
            max_count = 1,  -- Maximum number of this item to spawn
            entity    = "data/entities/items/wand_level_03.xml" -- The entity to spawn
        }
        ```
        *   Note: The first entry with `prob = 0` represents air and effectively spawns nothing. Skullflies are intended to spawn after this.
*   **`spawn_wands(x, y)`**:
    *   Calls the generic `spawn` function with the `g_items` table to place items.

### Other Placeholder Spawning Functions

The following functions are defined but do not contain implementation details in this snippet, indicating they are either handled elsewhere or are intended for future development.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_lamp(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`

### Stash Spawning (`spawn_stash`)

This function handles the potential spawning of a "stash" entity.

*   **`spawn_stash(x, y)`**:
    *   Includes a 20% chance of not spawning anything (`ProceduralRandom(x,y) < 0.17`).
    *   If the random check passes, it calls `entity_load_stash(x,y)` to load the stash.

## Registration

The biome registers its spawn functions with the game's director system.

*   **`RegisterSpawnFunction(0xffffeedd, "init")`**: Registers the `init` function for a specific biome ID.
*   **`RegisterSpawnFunction(0xffbf262b, "spawn_metportal")`**: Registers the `spawn_metportal` function for another biome ID.