---
title: Temple Altar Right Snowcastle Biome
category: biome
---

# Temple Altar Right Snowcastle Biome

This script defines the biome for the "Temple Altar Right Snowcastle" area in Noita. It handles the spawning of various entities, including shops, workshops, and decorative elements, based on specific spawn functions triggered by unique hexadecimal IDs.

## Core Functionality

The script relies on `dofile_once` to include essential helper functions for biome generation and item spawning. It then registers several spawn functions, each associated with a specific hexadecimal ID, which are called by the game engine at appropriate times during level generation.

### Key Spawn Functions and Their Purpose:

*   **`init(x, y, w, h)`**: The primary initialization function for the biome. It calls `spawn_altar_top` and loads the visual and background assets for the "altar_right_snowcastle" area.
*   **`spawn_hp(x, y)`**: Spawns a full HP pickup, likely for healing purposes.
*   **`spawn_shopitem(x, y)`**: Spawns a standard shop item.
*   **`spawn_cheap_shopitem(x, y)`**: Spawns a cheaper version of a shop item, utilizing the `generate_shop_item` function.
*   **`spawn_workshop(x, y)`**: Spawns a workshop building and a hint for its use.
*   **`spawn_workshop_extra(x, y)`**: Spawns an additional workshop building that allows for mod installations.
*   **`spawn_motordoor(x, y)`**: Spawns a specific type of temple door.
*   **`spawn_pressureplate(x, y)`**: Spawns a temple pressure plate.
*   **`spawn_lamp(x, y)` / `spawn_lamp_long(x, y)`**: Spawns temple lanterns with varying lengths.
*   **`spawn_control_workshop(x, y)`**: Spawns a workshop exit building.
*   **`spawn_perk_reroll(x, y)`**: Spawns a perk reroll item.
*   **`spawn_areachecks(x, y)`**: Spawns various "area check" entities, likely used for level progression or triggering events within the biome.
*   **`spawn_rubble(x, y)`**: Spawns decorative rubble props.
*   **`spawn_statue(x, y)`**: Spawns a temple statue.

## Entity Spawning Tables

The script defines tables that dictate the probability and types of entities to spawn for specific categories.

### `g_lamp` Table:

This table defines the possible temple lanterns that can be spawned.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                       | Total probability (not actively used here) |
| `prob`      | `1.0`                                     | Probability of spawning this entry        |
| `min_count` | `1`                                       | Minimum number of entities to spawn       |
| `max_count` | `1`                                       | Maximum number of entities to spawn       |
| `entity`    | `""`                                      | Placeholder, likely for no entity spawn   |
| `entity`    | `"data/entities/props/physics/temple_lantern.xml"` | The entity ID for a temple lantern        |

### `g_rubble` Table:

This table defines the various rubble props that can be spawned in the biome.

| Attribute   | Value                                         | Description                                     |
| :---------- | :-------------------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                           | Total probability (not actively used here)       |
| `prob`      | `2.0`                                         | Base probability for rubble spawning            |
| `min_count` | `1`                                           | Minimum number of rubble pieces to spawn        |
| `max_count` | `1`                                           | Maximum number of rubble pieces to spawn        |
| `entity`    | `""`                                          | Placeholder, likely for no entity spawn         |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Entity ID for rubble type 1                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` | Entity ID for rubble type 2                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_03.xml"` | Entity ID for rubble type 3                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_04.xml"` | Entity ID for rubble type 4                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_05.xml"` | Entity ID for rubble type 5                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_06.xml"` | Entity ID for rubble type 6                   |

## Unused/Placeholder Functions

Several functions are defined but appear to be empty or contain commented-out code, indicating they are either placeholders for future development or not currently used in this specific biome.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_all_perks` (contains a print statement indicating it should not be called)