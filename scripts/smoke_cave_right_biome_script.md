---
title: Smoke Cave Right Biome Script
category: scripts
---

# Smoke Cave Right Biome Script

This script defines the behavior and entity spawning for the "Smoke Cave Right" biome in Noita. It registers functions for initializing the biome and spawning music triggers.

## Core Functions

### `init(x, y, w, h)`
This is the primary initialization function for the biome. It loads the visual representation of the biome.

*   **`LoadPixelScene("data/biome_impl/smokecave_right.png", "", x, y, "", true)`**: Loads the pixel scene data for the Smoke Cave Right biome at the specified coordinates.

### `spawn_music_trigger(x, y)`
This function is responsible for spawning a music trigger entity within the biome.

*   **`EntityLoad("data/entities/buildings/music_trigger_smokecave.xml", x, y)`**: Loads the `music_trigger_smokecave.xml` entity at the given coordinates.

## Entity Spawning

The script includes a table `g_small_enemies` which defines probabilities and counts for spawning smaller enemy types.

### `g_small_enemies` Table

This table outlines the distribution of small enemies within the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for spawning from this table (currently 0).            |
| `prob`      | The probability of this specific enemy type spawning.                    |
| `min_count` | The minimum number of this enemy to spawn.                               |
| `max_count` | The maximum number of this enemy to spawn.                               |
| `entity`    | The XML path to the entity to spawn.                                     |

**Key Enemy Spawns:**

| Entity Path                                   | Probability | Min Count | Max Count |
| :-------------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/animals/slimeshooter.xml`      | 0.1         | 1         | 2         |
| `data/entities/animals/acidshooter.xml`       | 0.1         | 1         | 2         |
| `data/entities/animals/giantshooter.xml`      | 0.02        | 1         | 1         |
| `data/entities/animals/lasershooter.xml`      | 0.05        | 1         | 1         |

### `spawn_small_enemies(x, y)`
A helper function to call the spawning logic defined in `g_small_enemies`.

## Unimplemented Spawn Functions

The following functions are defined but have no implementation, indicating they are not used or are intended for future development within this specific biome script.

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