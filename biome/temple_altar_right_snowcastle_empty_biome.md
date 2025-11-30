---
title: Temple Altar Right Snowcastle Empty Biome
category: biome
---

# Temple Altar Right Snowcastle Empty Biome

This document details the configuration for the `temple_altar_right_snowcastle_empty.lua` biome script in Noita, focusing on its AI-assisted modding potential.

## Core Functionality

This script defines a specific biome within the game, likely a variation of the Temple area with a snowcastle theme and an empty altar. It registers various spawn functions for different game elements.

## Key Spawn Functions

The script registers several functions to be called at specific points or based on certain conditions. These are crucial for populating the biome with entities.

### Registered Spawn Functions

| Color Code | Function Name      | Description                                     |
| :--------- | :----------------- | :---------------------------------------------- |
| `0xffffeedd` | `init`             | Initializes the biome's core elements.          |
| `0xff6d934c` | `spawn_hp`         | Handles HP-related spawns (likely pickups).     |
| `0xff33934c` | `spawn_shopitem`   | Spawns shop items.                              |
| `0xff33935F` | `spawn_cheap_shopitem` | Spawns cheaper shop items.                      |
| `0xff10822d` | `spawn_workshop`   | Spawns workshop-related entities.               |
| `0xff5a822d` | `spawn_workshop_extra` | Spawns additional workshop entities.            |
| `0xffFAABBA` | `spawn_motordoor`  | Spawns motor doors.                             |
| `0xffFAABBB` | `spawn_pressureplate` | Spawns pressure plates.                         |
| `0xffA85454` | `spawn_control_workshop` | Spawns entities for workshop control.           |
| `0xff03DEAD` | `spawn_areachecks` | Handles area checks (e.g., for player presence). |
| `0xff7345DF` | `spawn_perk_reroll` | Spawns perk reroll mechanics.                   |
| `0xffc128ff` | `spawn_rubble`     | Spawns rubble props.                            |
| `0xffa7a707` | `spawn_lamp_long`  | Spawns long lamps.                              |
| `0xff9f2a00` | `spawn_statue`     | Spawns statues.                                 |

## Entity Spawning Tables

The script utilizes tables to define probabilities and entities for specific spawn types.

### `g_lamp` Table

This table defines the entities and probabilities for spawning lamps.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                       | Total probability (likely calculated).    |
| `prob`      | `1.0`                                     | Probability for the first entry.          |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `""`                                      | Empty entity (likely a placeholder).      |
| `prob`      | `1.0`                                     | Probability for the second entry.         |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `"data/entities/props/physics/temple_lantern.xml"` | The specific lamp entity to spawn.        |

### `g_rubble` Table

This table defines the entities and probabilities for spawning rubble.

| Attribute   | Value                                       | Description                                     |
| :---------- | :---------------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                       | Total probability (likely calculated).          |
| `prob`      | `2.0`                                     | Probability for the first entry.                |
| `min_count` | `1`                                       | Minimum number of entities to spawn.            |
| `max_count` | `1`                                       | Maximum number of entities to spawn.            |
| `entity`    | `""`                                      | Empty entity (likely a placeholder).            |
| `prob`      | `0.1`                                     | Probability for the second entry.               |
| `min_count` | `1`                                       | Minimum number of entities to spawn.            |
| `max_count` | `1`                                       | Maximum number of entities to spawn.            |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Specific rubble entity.                         |
| `prob`      | `0.1`                                     | Probability for the third entry.                |
| `min_count` | `1`                                       | Minimum number of entities to spawn.            |
| `max_count` | `1`                                       | Maximum number of entities to spawn.            |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` | Specific rubble entity.                         |
| ...         | ...                                       | ... (other rubble variations follow)            |

## Key Functions

### `init(x, y, w, h)`

This is the primary initialization function for the biome.

*   **`temple_random(x, y)`**: Likely calls a shared temple function to introduce random elements.
*   **`LoadBackgroundSprite(...)`**: Loads background visuals for the biome.
*   **`LoadPixelScene(...)`**: Loads specific pixel scene data to construct the biome's layout and visuals, including elements like `altar_top.png` and `altar_right_snowcastle.png`.

### `spawn_lamp(x, y)` and `spawn_lamp_long(x, y)`

These functions utilize the `g_lamp` table to spawn lamps at specified coordinates. The `spawn_lamp_long` function appears to have a slightly different parameter for spawn distance.

### `spawn_rubble(x, y)`

This function uses the `g_rubble` table to spawn various rubble props. The `spawn` function parameters `5, 0` likely control spawn spread and height.

### `spawn_statue(x, y)`

This function directly loads a specific temple statue entity: `data/entities/props/temple_statue_02.xml`.

## Modding Considerations

*   **Entity Replacement**: To change the types of lamps or rubble, modify the `entity` fields within their respective tables (`g_lamp`, `g_rubble`).
*   **Spawn Probabilities**: Adjust the `prob` values in the spawning tables to control how frequently certain entities appear.
*   **New Spawn Functions**: New spawn functions can be registered using `RegisterSpawnFunction` with unique color codes and corresponding Lua functions.
*   **Biome Layout**: The `LoadPixelScene` calls in `init` are critical for defining the visual structure of the biome. Modifying the `.png` files or the parameters of `LoadPixelScene` will alter the layout.
*   **Shared Functions**: The script relies on `dofile_once` for shared utility scripts like `director_helpers.lua` and `biome_scripts.lua`. Understanding these shared scripts is essential for advanced modding.