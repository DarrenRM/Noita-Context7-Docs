---
title: Niilo Testroom C Biome Configuration
category: scripts/biome
---

# Niilo Testroom C Biome Configuration

This document details the configuration for the "Niilo Testroom C" biome in Noita, focusing on its entity spawning properties.

## Biome Initialization

The `init` function is responsible for loading the visual representation of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/_examples/niilo_testroom_c.png", "", x, y, "", true )
end
```

-   **`LoadPixelScene`**: This function loads the biome's visual layer from a specified PNG file.
    -   `"data/biome_impl/_examples/niilo_testroom_c.png"`: The path to the pixel scene image.
    -   `x`, `y`: The coordinates where the scene will be loaded.
    -   `w`, `h`: Dimensions of the scene (often not explicitly used for placement).
    -   `""`: An empty string for a material to be applied to the scene (not used here).
    -   `true`: Indicates that the scene should be loaded.

## Prop Spawning Configuration (`g_props`)

The `g_props` table defines the probability and types of props that can spawn within this biome. The `spawn` function (called from `spawn_props`) uses this table to determine which entities to place.

```lua
g_props =
{
	total_prob = 0, -- This value is typically calculated by the game based on individual probabilities.
	{
		prob   		= 0.0, -- Zero probability, effectively disabled.
		min_count	= 0,
		max_count	= 0,
		entity 	= ""
	},
	-- ... other prop definitions ...
}
```

### Key Prop Spawning Attributes:

-   **`prob`**: The probability of this specific entity spawning. Higher values mean a greater chance.
-   **`min_count`**: The minimum number of this entity to spawn if selected.
-   **`max_count`**: The maximum number of this entity to spawn if selected.
-   **`entity`**: The XML file path for the entity to spawn.

### Prop Distribution:

The following table summarizes the key props and their spawn probabilities within `g_props`:

| Entity Path                                     | Probability | Min Count | Max Count |
| :---------------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/props/physics_box_explosive.xml` | 0.3         | 1         | 1         |
| `data/entities/props/physics_barrel_radioactive.xml` | 0.3         | 1         | 1         |
| `data/entities/props/physics_barrel_oil.xml`    | 0.4         | 1         | 1         |
| `data/entities/props/physics_pressure_tank.xml` | 0.1         | 1         | 1         |
| `data/entities/props/physics_propane_tank.xml`  | 0.1         | 1         | 1         |
| `data/entities/props/physics_stone_01.xml`      | 0.15        | 1         | 1         |
| `data/entities/props/physics_stone_02.xml`      | 0.15        | 1         | 1         |
| `data/entities/props/physics_stone_03.xml`      | 0.15        | 1         | 1         |
| `data/entities/props/physics_skull_01.xml`      | 0.05        | 1         | 1         |
| `data/entities/props/physics_skull_02.xml`      | 0.05        | 1         | 1         |
| `data/entities/props/physics_skull_03.xml`      | 0.05        | 1         | 1         |

*Note: The `total_prob` is not explicitly set and is likely calculated by the game engine.*

## Entity Spawning Functions

The following functions are defined but currently empty, indicating they are placeholders or not actively used for spawning specific entity types in this biome configuration.

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
	spawn(g_props,x,y) -- This function calls the prop spawning logic.
end

function load_pixel_scene2( x, y )
end

function load_pixel_scene4( x, y )
end
```