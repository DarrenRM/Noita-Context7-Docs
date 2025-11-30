---
title: Snowcastle Hourglass Chamber Biome
category: biome
---

# Snowcastle Hourglass Chamber Biome

This document details the configuration for the Snowcastle Hourglass Chamber biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Configuration

The `snowcastle_hourglass_chamber.lua` script defines the primary elements and spawning logic for this specific biome.

### Initialization and Visuals

The `init` function is responsible for loading the visual assets of the biome.

*   **`init(x, y, w, h)`**:
    *   Loads the main biome pixel scene: `data/biome_impl/snowcastle/hourglass_chamber.png`.
    *   Loads the background for the biome: `data/biome_impl/snowcastle/hourglass_chamber_background.png`.

### Registered Spawn Functions

These functions are registered to be called at specific points during level generation.

*   **`RegisterSpawnFunction( 0xff55AF8C, "spawn_skulls" )`**: Registers a function to spawn skulls.
*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function for biome initialization.
*   **`RegisterSpawnFunction( 0xff366178, "spawn_teleporter" )`**: Registers a function to spawn a teleporter.

## Entity Spawning Tables

These tables define the probabilities and entities that can be spawned within the biome.

### `g_items`

This table governs the spawning of items, particularly wands.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                 | Total probability (calculated dynamically).     |
| `prob`      | `1`                                 | Probability of this item being selected.        |
| `min_count` | `1`                                 | Minimum number of items to spawn.               |
| `max_count` | `1`                                 | Maximum number of items to spawn.               |
| `entity`    | `data/entities/items/wand_level_03.xml` | Entity to spawn (Level 3 Wand).                 |
| `entity`    | `data/entities/items/wand_unshuffle_02.xml` | Entity to spawn (Unshuffle Wand 2).             |

### `g_skulls`

This table defines the probability of spawning various skull and bone props.

| Attribute | Value                                   | Description                               |
| :-------- | :-------------------------------------- | :---------------------------------------- |
| `prob`    | `6`                                     | Probability for an empty spawn slot.      |
| `prob`    | `1.5`                                   | Probability for `physics_skull_01.xml`.   |
| `prob`    | `1.5`                                   | Probability for `physics_skull_02.xml`.   |
| `prob`    | `1.5`                                   | Probability for `physics_skull_03.xml`.   |
| `prob`    | `0.5`                                   | Probability for `physics_bone_01.xml`.    |
| `prob`    | `0.5`                                   | Probability for `physics_bone_02.xml`.    |
| `prob`    | `0.5`                                   | Probability for `physics_bone_03.xml`.    |
| `prob`    | `0.5`                                   | Probability for `physics_bone_04.xml`.    |
| `prob`    | `0.5`                                   | Probability for `physics_bone_05.xml`.    |
| `prob`    | `0.5`                                   | Probability for `physics_bone_06.xml`.    |
| `min_count`| `1`                                     | Minimum number of props to spawn.         |
| `max_count`| `1`                                     | Maximum number of props to spawn.         |
| `offset_y`| `0`                                     | Vertical offset for spawned entities.     |

### `g_stones`

This table defines the probability of spawning stone-related props.

| Attribute | Value                               | Description                               |
| :-------- | :---------------------------------- | :---------------------------------------- |
| `prob`    | `2`                                 | Probability for `stonepile.xml`.          |
| `prob`    | `1.5`                               | Probability for `physics_stone_01.xml`.   |
| `prob`    | `1.5`                               | Probability for `physics_stone_02.xml`.   |
| `prob`    | `1.5`                               | Probability for `physics_stone_03.xml`.   |
| `prob`    | `1.5`                               | Probability for `physics_stone_04.xml`.   |
| `prob`    | `4`                                 | Probability for an empty spawn slot.      |
| `min_count`| `1`                                 | Minimum number of props to spawn.         |
| `max_count`| `1`                                 | Maximum number of props to spawn.         |
| `offset_y`| `0`                                 | Vertical offset for spawned entities.     |

### `g_lamp`

This table controls the spawning of temple lanterns.

| Attribute | Value                                   | Description                               |
| :-------- | :-------------------------------------- | :---------------------------------------- |
| `prob`    | `0.25`                                  | Probability for an empty spawn slot.      |
| `prob`    | `1.0`                                   | Probability for `temple_lantern.xml`.     |
| `min_count`| `1`                                     | Minimum number of lamps to spawn.         |
| `max_count`| `1`                                     | Maximum number of lamps to spawn.         |
| `entity`  | `data/entities/props/physics/temple_lantern.xml` | Entity to spawn (Temple Lantern).         |

## Custom Spawn Functions

These functions are called by the registered spawn functions to perform specific actions.

*   **`spawn_lamp(x, y)`**: Spawns entities from the `g_lamp` table at the given coordinates.
*   **`spawn_skulls(x, y)`**: Spawns entities from the `g_skulls` table at the given coordinates.
*   **`spawn_teleporter(x, y)`**: Loads the `teleport_hourglass_return.xml` entity at the given coordinates.
*   **`spawn_items(x, y)`**:
    *   Sets a random seed based on coordinates.
    *   Calls `make_random_card(x,y)` to spawn a random card.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, indicating they are either placeholders or handled by other scripts.

*   `spawn_shopitem( x, y )`
*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_props(x, y)`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`