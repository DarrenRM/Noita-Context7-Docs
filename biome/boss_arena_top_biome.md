---
title: Boss Arena Top Biome
category: biome
---

---

# Boss Arena Top Biome

This document describes the configuration for the "Boss Arena Top" biome in Noita, focusing on its core elements relevant to AI-assisted modding.

## Core Biome Configuration

The `boss_arena_top.lua` script defines the fundamental aspects of this biome, including its visual representation and the entities that can spawn within it.

### Initialization

The `init` function is responsible for loading the visual layer of the biome.

```lua
function init(x, y, w, h)
	LoadPixelScene( "data/biome_impl/boss_arena_top.png", "", x, y, "", true )
end
```

*   **`LoadPixelScene`**: This function loads the pixel data that defines the visual layout and terrain of the biome.
    *   `"data/biome_impl/boss_arena_top.png"`: The path to the image file containing the biome's pixel data.
    *   `x`, `y`: The coordinates where the biome is placed.
    *   `w`, `h`: The width and height of the biome area.
    *   `""`: An empty string, likely for additional parameters not used here.
    *   `true`: A boolean flag, potentially indicating whether to use this scene as the primary visual.

### Spawn Functions

Several spawn functions are defined but are intentionally left empty (`end`). This suggests that the spawning logic for this biome is handled by external systems or is not directly implemented within this script.

*   `spawn_small_enemies( x, y ) end`
*   `spawn_big_enemies( x, y ) end`
*   `spawn_items( x, y ) end`
*   `spawn_props( x, y ) end`
*   `spawn_orb( x, y ) end`
*   `load_pixel_scene( x, y ) end`
*   `load_pixel_scene2( x, y ) end`
*   `spawn_unique_enemy( x, y ) end`
*   `spawn_ghostlamp( x, y ) end`
*   `spawn_candles( x, y ) end`
*   `spawn_potions( x, y ) end`

### Lamp Spawning

A specific function `spawn_lamp` is implemented to handle the spawning of lamps within the biome.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x,y,0,0)
end
```

*   **`spawn(g_lamp, x, y, 0, 0)`**: This calls the generic `spawn` function to place entities defined in the `g_lamp` table at the given `x`, `y` coordinates.

### Global Lamp Configuration (`g_lamp`)

The `g_lamp` table defines the properties and entities associated with lamps that can spawn.

```lua
g_lamp =
{
	total_prob = 0, -- This value is often used to normalize probabilities, 0 might indicate it's not directly used for normalization here.
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "" -- An empty entity string might represent a default or no specific entity for this probability.
	},
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics/temple_lantern.xml" -- The specific entity to spawn.
	},
}
```

*   **`prob`**: The probability of this specific entry being chosen.
*   **`min_count` / `max_count`**: The minimum and maximum number of entities to spawn for this entry.
*   **`entity`**: The XML path to the entity to be spawned. In this case, `"data/entities/props/physics/temple_lantern.xml"` is the primary entity.

## Dependencies

This script relies on external helper functions and definitions.

*   **`CHEST_LEVEL = 3`**: A constant likely used by other systems to determine chest rarity or type within this biome.
*   **`dofile_once("data/scripts/director_helpers.lua")`**: Loads utility functions for managing game directors and spawning.
*   **`dofile_once("data/scripts/biome_scripts.lua")`**: Loads general biome-related functions and definitions.
*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called at a specific point during biome initialization, identified by the color `0xffffeedd`.