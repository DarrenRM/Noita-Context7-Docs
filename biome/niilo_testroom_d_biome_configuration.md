---
title: Niilo Testroom D Biome Configuration
category: biome
---

# Niilo Testroom D Biome Configuration

This document details the configuration for the "Niilo Testroom D" biome in Noita, focusing on its entity spawning properties.

## Biome Initialization

The `init` function is responsible for loading the visual representation of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/_examples/niilo_testroom_d.png", "", x, y, "", true )
end
```

-   **`LoadPixelScene`**: This function loads a predefined pixel scene to define the biome's layout and visual elements.
    -   The first argument specifies the path to the `.png` file used for the scene.
    -   The remaining arguments control positioning and other loading parameters.

## Entity Spawning Properties (`g_props`)

The `g_props` table defines the probability and count of various props that can spawn within this biome. The `spawn` function, called by `spawn_props`, uses this table to determine which entities to place.

```lua
g_props =
{
	total_prob = 0, -- This is calculated dynamically, not explicitly set here.
	{
		prob   		= 0.0, -- Zero probability, effectively disabled.
		min_count	= 0,
		max_count	= 0,
		entity 	= ""
	},
	{
		prob   		= 0.3, -- 30% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_box_explosive.xml"
	},
	{
		prob   		= 0.3, -- 30% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_barrel_radioactive.xml"
	},
	{
		prob   		= 0.4, -- 40% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_barrel_oil.xml"
	},
	{
		prob   		= 0.1, -- 10% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_pressure_tank.xml"
	},
	{
		prob   		= 0.1, -- 10% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_propane_tank.xml"
	},
	{
		prob   		= 0.15, -- 15% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_stone_01.xml"
	},
	{
		prob   		= 0.15, -- 15% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_stone_02.xml"
	},
	{
		prob   		= 0.15, -- 15% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_stone_03.xml"
	},
	{
		prob   		= 0.05, -- 5% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_01.xml"
	},
	{
		prob   		= 0.05, -- 5% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_02.xml"
	},
	{
		prob   		= 0.05, -- 5% chance
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_03.xml"
	},
}
```

### Key Attributes:

-   **`prob`**: The probability of this entity being selected for spawning.
-   **`min_count` / `max_count`**: The minimum and maximum number of this entity to spawn if selected.
-   **`entity`**: The path to the `.xml` file defining the entity to spawn.

## Spawn Functions

The following functions are defined but currently empty, indicating they are placeholders or not actively used for spawning in this specific biome configuration.

### `spawn_small_enemies(x, y)`

Placeholder for spawning small enemy types.

### `spawn_big_enemies(x, y)`

Placeholder for spawning large enemy types.

### `spawn_items(x, y)`

Placeholder for spawning items.

### `spawn_lamp(x, y)`

Placeholder for spawning lamps.

### `spawn_props(x, y)`

This function is responsible for spawning props within the biome, utilizing the `g_props` table.

```lua
function spawn_props(x, y)
	spawn(g_props,x,y)
end
```

### `load_pixel_scene2( x, y )`

Placeholder function.

### `load_pixel_scene4( x, y )`

Placeholder function.