---
title: Snowcastle Cavern Biome Script
category: scripts/
---

# Snowcastle Cavern Biome Script

This script defines the behavior and entity spawning for the Snowcastle Cavern biome in Noita. It handles the loading of pixel scenes and registers various spawn functions for entities like lamps, props, vines, and special hourglasses.

## Core Biome Logic

The `init` function is the primary entry point for this biome. It determines whether to load a left or right-facing side cavern based on a procedural random value and the cavern's position. It avoids spawning when the world is looping to prevent placement issues.

### `init(x, y, w, h)`

*   **Purpose:** Initializes the biome by loading a specific pixel scene.
*   **Parameters:**
    *   `x`: The x-coordinate of the biome.
    *   `y`: The y-coordinate of the biome.
    *   `w`: The width of the biome.
    *   `h`: The height of the biome.
*   **Key Logic:**
    *   Randomly decides to spawn a `side_cavern_right` or `side_cavern_left`.
    *   Loads the corresponding `.png` (visual), `.png` (visual overlay), and `.png` (background) files.
    *   Applies a small horizontal offset (`x-50` or `x+50`) to the spawn position.
    *   Prevents spawning if `x` is outside a reasonable range to avoid world-looping issues.

## Registered Spawn Functions

These functions are registered with specific color IDs and are called by the game engine to spawn entities at designated points within the biome.

### `RegisterSpawnFunction(color_id, function_name)`

*   **Purpose:** Associates a specific color ID with a function to be executed when that color is encountered during biome generation.

| Color ID     | Function Name                 | Description                                      |
| :----------- | :---------------------------- | :----------------------------------------------- |
| `0xffC8C800` | `spawn_lamp`                  | Spawns lamps.                                    |
| `0xff80FF5A` | `spawn_vines`                 | Spawns vines.                                    |
| `0xff33934c` | `spawn_shopitem`              | Spawns a shop item.                              |
| `0xffffeedd` | `init`                        | The main biome initialization function.          |
| `0xff03deaf` | `spawn_fish`                  | Spawns fish entities.                            |
| `0xffff2974` | `spawn_hourglass_blood`       | Spawns a blood hourglass building.               |
| `0xffff9122` | `spawn_hourglass_master`      | Spawns a master hourglass and teleport hourglass. |
| `0xff216bff` | `spawn_hourglass_music_trigger` | Spawns a music hourglass trigger.                |

## Entity Spawn Tables

These tables define the probabilities and entities to be spawned by the registered functions.

### `g_lamp`

*   **Purpose:** Defines the entities and their probabilities for spawning lamps.
*   **Key Entries:**
    *   A 20% chance to spawn nothing.
    *   An 80% chance to spawn a `lantern_small.xml`.

### `g_props`

*   **Purpose:** Defines the entities and their probabilities for spawning physics props.
*   **Key Entries:**
    *   A 20% chance to spawn nothing.
    *   A 50% chance to spawn `physics_box_explosive.xml`.
    *   A 50% chance to spawn `physics_propane_tank.xml`.
    *   A 10% chance to spawn `physics_seamine.xml` with a slight vertical offset.

### `g_ghostlamp`

*   **Purpose:** Defines the entities and their probabilities for spawning ghostly lamps.
*   **Key Entries:**
    *   A 100% chance to spawn `physics_chain_torch_ghostly.xml` with a vertical offset.

### `g_vines`

*   **Purpose:** Defines the entities and their probabilities for spawning various types of vines.
*   **Key Entries:**
    *   Multiple entries with varying probabilities for different vine lengths (`verlet_vine.xml`, `verlet_vine_long.xml`, `verlet_vine_short.xml`, `verlet_vine_shorter.xml`).
    *   Includes a chance to spawn nothing.

### `g_fish`

*   **Purpose:** Defines the entities and their probabilities for spawning fish.
*   **Key Entries:**
    *   A 100% chance to spawn 2 to 5 `fish.xml` entities.

## Helper Spawn Functions

These are the actual functions called by the game that utilize the spawn tables.

### `spawn_shopitem(x, y)`

*   **Purpose:** Generates a shop item at the given coordinates.

### `spawn_lamp(x, y)`

*   **Purpose:** Spawns entities defined in `g_lamp` at the given coordinates.

### `spawn_props(x, y)`

*   **Purpose:** Spawns entities defined in `g_props` at the given coordinates with a slight vertical adjustment.

### `spawn_vines(x, y)`

*   **Purpose:** Spawns entities defined in `g_vines` at the given coordinates with a slight offset.

### `spawn_barricade(x, y)`

*   **Purpose:** Spawns entities defined in `g_barricade` (not fully defined in this snippet, likely from another file).

### `spawn_fish(x, y)`

*   **Purpose:** Spawns entities defined in `g_fish` at the given coordinates.

### `spawn_hourglass_blood(x, y)`

*   **Purpose:** Loads the `hourglass_blood.xml` entity at the given coordinates.

### `spawn_hourglass_master(x, y)`

*   **Purpose:** Loads both `hourglass_master.xml` and `teleport_hourglass.xml` entities at the given coordinates.

### `spawn_hourglass_music_trigger(x, y)`

*   **Purpose:** Loads the `hourglass_music.xml` entity at the given coordinates. This is noted to have a separate spawn to maintain symmetry.