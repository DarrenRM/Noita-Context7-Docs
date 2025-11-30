---
title: Niilo Testroom Biome
category: biome
---

# Niilo Testroom Biome

This document describes the configuration for the "Niilo Testroom" biome in Noita, focusing on its entity spawning properties.

## Biome Initialization

The `init` function is responsible for loading the visual representation of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/_examples/niilo_testroom.png", "", x, y, "", true )
end
```

This function uses `LoadPixelScene` to load the `niilo_testroom.png` image as the biome's visual layout.

## Prop Spawning Configuration (`g_props`)

The `g_props` table defines the probability and count for various physics-based props that can spawn within this biome. The `total_prob` is calculated automatically based on the individual probabilities.

| Probability (`prob`) | Minimum Count (`min_count`) | Maximum Count (`max_count`) | Entity Path                                       |
| :------------------- | :-------------------------- | :-------------------------- | :------------------------------------------------ |
| 0.0                  | 0                           | 0                           | (Not used)                                        |
| 0.3                  | 1                           | 1                           | `data/entities/props/physics_box_explosive.xml`   |
| 0.3                  | 1                           | 1                           | `data/entities/props/physics_barrel_radioactive.xml` |
| 0.4                  | 1                           | 1                           | `data/entities/props/physics_barrel_oil.xml`      |
| 0.1                  | 1                           | 1                           | `data/entities/props/physics_pressure_tank.xml`   |
| 0.1                  | 1                           | 1                           | `data/entities/props/physics_propane_tank.xml`    |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_01.xml`        |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_02.xml`        |
| 0.15                 | 1                           | 1                           | `data/entities/props/physics_stone_03.xml`        |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_01.xml`        |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_02.xml`        |
| 0.05                 | 1                           | 1                           | `data/entities/props/physics_skull_03.xml`        |

The `spawn_props` function utilizes this table to spawn entities based on their defined probabilities.

```lua
function spawn_props(x, y)
	spawn(g_props,x,y)
end
```

## Other Spawn Functions

The following functions are defined but currently empty, indicating they do not spawn any specific entities in this biome.

```lua
function spawn_small_enemies(x, y)
end

function spawn_big_enemies(x, y)
end

function spawn_items(x, y)
end

function spawn_lamp(x, y)
end

function load_pixel_scene2( x, y )
end

function load_pixel_scene4( x, y )
end
```