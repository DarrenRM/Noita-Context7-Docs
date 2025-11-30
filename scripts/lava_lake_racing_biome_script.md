---
title: Lava Lake Racing Biome Script
category: scripts/
---

# Lava Lake Racing Biome Script

This script defines the behavior and entities for the Lava Lake Racing biome in Noita. It handles the loading of the biome's visual assets and the spawning of specific racing-related entities.

## Core Functionality

The script registers several spawn functions that are triggered by specific entity IDs within the biome's pixel scene data. These functions are responsible for placing key elements of the racing experience.

### Registered Spawn Functions

| Entity ID (Hex) | Function Name        | Description                               |
| :-------------- | :------------------- | :---------------------------------------- |
| `0xffffeedd`    | `init`               | Initializes the biome and loads its visuals. |
| `0xffff6630`    | `spawn_checkpoint_1` | Spawns the first checkpoint.              |
| `0xff52f100`    | `spawn_checkpoint_2` | Spawns the second checkpoint.             |
| `0xff9e33ff`    | `spawn_finish_line`  | Spawns the finish line.                   |
| `0xff679c00`    | `spawn_racing_cart`  | Spawns the player's racing cart.          |
| `0xffcaca00`    | `spawn_stopwatches`  | Spawns the lap timer display.             |
| `0xffb8ffe1`    | `spawn_skulls`       | Spawns decorative skulls.                 |

## Biome Initialization (`init`)

The `init` function is called when the biome is first loaded. It's responsible for setting up the visual environment.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/lavalake_racing.png", "", x, y, "data/biome_impl/lavalake_racing_background.png", true )
end
```

*   **`LoadPixelScene`**: This function loads the primary visual layer (`lavalake_racing.png`) and a background layer (`lavalake_racing_background.png`) for the biome. The `true` argument likely indicates that the background should be rendered.

## Entity Spawning Functions

These functions are called by the `RegisterSpawnFunction` calls and are responsible for instantiating specific game entities within the biome.

### `spawn_racing_cart`

Spawns the player's racing vehicle.

```lua
function spawn_racing_cart( x, y )
	EntityLoad( "data/entities/buildings/racing_cart.xml", x, y )
end
```

### `spawn_checkpoint_1` and `spawn_checkpoint_2`

Spawns generic racing checkpoints. Tags are added to differentiate them.

```lua
function spawn_checkpoint_1( x, y )
	local eid = EntityLoad( "data/entities/buildings/racing_checkpoint.xml", x, y )
	EntityAddTag(eid, "checkpoint_1" )
end

function spawn_checkpoint_2( x, y )
	local eid = EntityLoad( "data/entities/buildings/racing_checkpoint.xml", x, y )
	EntityAddTag(eid, "checkpoint_2" )
end
```

### `spawn_finish_line`

Spawns the finish line entity, also using the checkpoint XML but with a specific tag.

```lua
function spawn_finish_line( x, y )
	local eid = EntityLoad( "data/entities/buildings/racing_checkpoint.xml", x, y )
	EntityAddTag(eid, "finish_line" )
end
```

### `spawn_stopwatches`

Spawns the UI elements for tracking race times.

```lua
function spawn_stopwatches( x, y )
	local offset = 26
	y = y + 0.5 -- Adjusts vertical position slightly
	local eid = EntityLoad( "data/entities/buildings/racing_stopwatch.xml", x, y )
	EntityAddTag(eid, "stopwatch_lap" ) -- Current lap time
	eid = EntityLoad( "data/entities/buildings/racing_stopwatch.xml", x + offset, y )
	EntityAddTag(eid, "stopwatch_prev_lap" ) -- Previous lap time
	eid = EntityLoad( "data/entities/buildings/racing_stopwatch.xml", x + offset * 2, y )
	EntityAddTag(eid, "stopwatch_best_lap" ) -- Best lap time
end
```

### `spawn_skulls`

Spawns decorative skulls with a probability-based selection.

```lua
function spawn_skulls(x, y)
	spawn(g_skulls,x,y-5) -- Spawns skulls slightly below the trigger point
end

g_skulls =
{
	total_prob = 0, -- This field is not used in the provided snippet, likely calculated elsewhere or intended for future use.
	{
		prob   		= 0.5,
		min_count	= 1,
		max_count	= 1,
		entity 	= "", -- Empty entity, likely a placeholder or unused.
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_01.xml"
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_02.xml"
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_skull_03.xml"
	},
}
```

*   **`g_skulls` Table**: This table defines the possible skull entities to spawn, their relative probabilities, and the minimum/maximum count for each. The `spawn` function (likely from `director_helpers.lua`) handles the random selection based on these probabilities.

## Unused/Placeholder Functions

The following functions are defined but have empty bodies, indicating they are not used in this specific biome script or are placeholders for future implementation.

*   `spawn_small_enemies`
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
*   `spawn_wands`