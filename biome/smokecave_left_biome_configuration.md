---
title: Smokecave Left Biome Configuration
category: biome
---

# Smokecave Left Biome Configuration

This document details the configuration for the "Smokecave Left" biome in Noita, focusing on its entity spawning and scene loading.

## Core Biome Functions

The `smokecave_left.lua` script registers specific functions to be called during biome initialization and entity spawning.

### Spawn Functions

| Function Name     | Description                                       |
| :---------------- | :------------------------------------------------ |
| `init`            | Loads the primary pixel scene for the biome.      |
| `spawn_metportal` | Spawns a specific metroid portal entity.          |

## Entity Spawning Configuration

The biome defines a table `g_small_enemies` to manage the probability and types of smaller enemies that can spawn.

### `g_small_enemies` Table

This table outlines the distribution of smaller enemy entities within the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for spawning from this group (currently unused).       |
| `prob`      | The probability of this specific entity spawning.                        |
| `min_count` | The minimum number of this entity to spawn.                              |
| `max_count` | The maximum number of this entity to spawn.                              |
| `entity`    | The path to the entity's XML file.                                       |

**Key Entities and Probabilities:**

| Entity Path                                   | Probability | Min Count | Max Count |
| :-------------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/animals/slimeshooter.xml`      | 0.1         | 1         | 2         |
| `data/entities/animals/acidshooter.xml`       | 0.1         | 1         | 2         |
| `data/entities/animals/giantshooter.xml`      | 0.02        | 1         | 1         |
| `data/entities/animals/lasershooter.xml`      | 0.05        | 1         | 1         |

*Note: An entry with `entity = ""` and `prob = 0.1` exists, representing air, and does not spawn any entities.*

### `spawn_small_enemies` Function

This function utilizes the `g_small_enemies` table to spawn entities at specified coordinates.

```lua
function spawn_small_enemies(x, y)
	spawn(g_small_enemies,x,y)
end
```

## Unused/Placeholder Functions

Several functions are defined but currently have empty implementations, indicating they are not used or are placeholders for future development.

*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `spawn_lamp`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`

## Scene Loading

The `init` function is responsible for loading the visual representation of the Smokecave Left biome.

### `init` Function

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/smokecave_left.png", "", x, y, "", true )
end
```

This function loads the pixel scene from `data/biome_impl/smokecave_left.png` at the given coordinates.

## Special Entity Spawning

The `spawn_metportal` function handles the placement of a specific teleportation entity.

### `spawn_metportal` Function

```lua
function spawn_metportal( x, y )
	EntityLoad( "data/entities/buildings/teleport_smokecave.xml", x, y )
end
```

This function loads the `teleport_smokecave.xml` entity at the specified coordinates.