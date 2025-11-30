---
title: Niilo Testroom B Biome Configuration
category: biome
---

---

# Niilo Testroom B Biome Configuration

This document details the configuration for the "Niilo Testroom B" biome in Noita, focusing on its entity spawning properties.

## Biome Initialization

The `init` function is responsible for loading the visual representation of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/_examples/niilo_testroom_b.png", "", x, y, "", true )
end
```

-   **`LoadPixelScene`**: Loads the biome's visual layer from a specified PNG file.

## Entity Spawning Properties (`g_props`)

This table defines the probability and count of various physics-based props that can spawn within this biome. The `total_prob` is calculated based on the sum of individual probabilities.

| Probability (`prob`) | Minimum Count (`min_count`) | Maximum Count (`max_count`) | Entity XML Path                                      |
| :------------------- | :-------------------------- | :-------------------------- | :--------------------------------------------------- |
| 0.0                  | 0                           | 0                           | (Base entry, likely for initialization)              |
| 0.3                  | 1                           | 1                           | `data/entities/props/physics_box_explosive.xml`      |
| 0.3                  | 1                           | 1                           | `data/entities/props/physics_barrel_radioactive.xml` |
| 0.4                  | 1                           | 1                           | `data/entities/props/physics_barrel_oil.xml`         |
| 0.1                  | 1                           | 1                           | `data/entities/props/physics_pressure_tank.xml`      |
| 0.1                  | 1                           | 1                           | `data/entities/props/physics_propane_tank.xml`       |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_01.xml`           |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_02.xml`           |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_03.xml`           |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_01.xml`           |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_02.xml`           |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_03.xml`           |

*Note: The `total_prob` is not explicitly defined but would be the sum of all non-zero probabilities.*

## Spawn Functions

These functions are placeholders and do not currently implement any entity spawning logic for this specific biome.

```lua
function spawn_small_enemies(x, y)
end

function spawn_big_enemies(x, y)
end

function spawn_items(x, y)
end

function spawn_lamp(x, y)
end

function spawn_props(x, y)
	spawn(g_props,x,y)
end

function load_pixel_scene2( x, y )
end

function load_pixel_scene4( x, y )
end
```

-   **`spawn_props(x, y)`**: This is the active function that utilizes the `g_props` table to spawn physics entities at the specified coordinates.