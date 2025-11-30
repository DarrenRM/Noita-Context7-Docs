---
title: Smokecave Middle Biome Script
category: scripts/biome
---

# Smokecave Middle Biome Script

This script defines the spawning logic and initial setup for the "Smokecave Middle" biome in Noita. It registers a spawn function and defines a table for small enemy probabilities.

## Core Biome Functions

The script includes default biome functions that are called if a more specific biome function isn't found.

### `init(x, y, w, h)`

This is the primary initialization function for the Smokecave Middle biome.

*   **Purpose**: Loads the pixel scene that defines the visual layout and initial elements of the biome.
*   **Parameters**:
    *   `x`, `y`: Coordinates for the biome's placement.
    *   `w`, `h`: Dimensions of the biome.
*   **Action**: Calls `LoadPixelScene` with the specific pixel scene file for this biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/smokecave_middle.png", "", x, y, "", true )
end
```

## Enemy Spawning

The script defines a table `g_small_enemies` to manage the probability and types of small enemies that can spawn within this biome.

### `g_small_enemies` Table

This table dictates the distribution of smaller enemy entities.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| Total probability for spawning enemies from this table.                  |
| `prob`      | The probability of a specific enemy type spawning.                       |
| `min_count` | The minimum number of this enemy type to spawn.                          |
| `max_count` | The maximum number of this enemy type to spawn.                          |
| `entity`    | The file path to the entity XML definition for the enemy.                |

**Key Enemy Entries:**

| `prob` | `min_count` | `max_count` | `entity`                                  | Notes                               |
| :----- | :---------- | :---------- | :---------------------------------------- | :---------------------------------- |
| 0.1    | 1           | 2           | `data/entities/animals/slimeshooter.xml`  |                                     |
| 0.1    | 1           | 2           | `data/entities/animals/acidshooter.xml`   |                                     |
| 0.02   | 1           | 1           | `data/entities/animals/giantshooter.xml`  | Lower probability for this variant. |
| 0.05   | 1           | 1           | `data/entities/animals/lasershooter.xml`  |                                     |

*Note: The table includes entries with `min_count = 0` and `max_count = 0` for air, indicating no spawns at certain probability thresholds.*

### `spawn_small_enemies(x, y)`

A helper function to trigger the spawning of small enemies based on the `g_small_enemies` table.

```lua
function spawn_small_enemies(x, y)
	spawn(g_small_enemies,x,y)
end
```

## Unused/Placeholder Functions

The following functions are defined but have empty implementations, suggesting they are either placeholders for future development or not utilized in this specific biome script.

*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`

## Initialization

The script registers a global spawn function that will be called by the game's director system.

### `RegisterSpawnFunction( 0xffffeedd, "init" )`

*   **Purpose**: Registers the `init` function to be called when the game's director system determines it's time to initialize this biome.
*   **`0xffffeedd`**: Likely an internal identifier or color code associated with the Smokecave Middle biome.
*   **`"init"`**: The name of the function to be executed.