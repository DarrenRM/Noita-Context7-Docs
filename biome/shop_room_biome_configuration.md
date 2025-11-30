---
title: Shop Room Biome Configuration
category: biome
---

# Shop Room Biome Configuration

This document details the configuration for the "shop_room" biome in Noita, focusing on its entity spawning and initialization logic. This biome is designed to represent a shop area within the game.

## Core Functionality

The `shop_room.lua` script defines the behavior and content of the shop biome. It relies on several helper functions and registers specific spawn functions for various game elements.

### Initialization

The primary initialization function `init(x, y, w, h)` is responsible for loading the visual representation of the shop room.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/shop_room.png", "", x, y, "", true )
end
```

*   **`LoadPixelScene`**: This function loads a pixel scene defined by `"data/biome_impl/shop_room.png"`. This image likely dictates the layout, walls, and basic structure of the shop room.

## Registered Spawn Functions

The script registers several functions to be called at specific points or with specific identifiers during gameplay. These functions are crucial for populating the shop room with items, buildings, and interactive elements.

### Key Spawn Functions:

*   **`init` (0xffffeedd)**: The main initialization function for the biome.
*   **`spawn_hp` (0xff6d934c)**: Spawns health-related entities.
*   **`spawn_shopitem` (0xff33934c)**: Spawns standard shop items.
*   **`spawn_cheap_shopitem` (0xff33935F)**: Spawns cheaper shop items.
*   **`spawn_workshop` (0xff10822d)**: Spawns a workshop building.
*   **`spawn_workshop_extra` (0xff5a822d)**: Spawns an additional workshop variant.
*   **`spawn_motordoor` (0xffFAABBA)**: Spawns a motor door.
*   **`spawn_pressureplate` (0xffFAABBB)**: Spawns a pressure plate.

### Detailed Spawn Function Logic:

#### `spawn_hp(x, y)`

This function spawns a full health pickup and a coop respawn point.

```lua
function spawn_hp( x, y )
	EntityLoad( "data/entities/items/pickup/heart_fullhp_temple.xml", x, y )
	EntityLoad( "data/entities/buildings/coop_respawn.xml", x, y )
end
```

#### `spawn_shopitem(x, y)`

This function calls a helper to generate a shop item.

```lua
function spawn_shopitem( x, y )
	-- EntityLoad( "data/entities/items/shop_item.xml", x, y ) -- Commented out, likely superseded by generate_shop_item
	generate_shop_item( x, y, false )
end
```

#### `spawn_cheap_shopitem(x, y)`

Similar to `spawn_shopitem`, but generates a cheaper variant.

```lua
function spawn_cheap_shopitem( x, y )
	-- EntityLoad( "data/entities/items/shop_item.xml", x, y ) -- Commented out
	generate_shop_item( x, y, true )
end
```

#### `spawn_workshop(x, y)`

Spawns the standard workshop building.

```lua
function spawn_workshop( x, y )
	EntityLoad( "data/entities/buildings/workshop.xml", x, y )
end
```

#### `spawn_workshop_extra(x, y)`

Spawns a workshop variant that might allow mods.

```lua
function spawn_workshop_extra( x, y )
	EntityLoad( "data/entities/buildings/workshop_allow_mods.xml", x, y )
end
```

#### `spawn_motordoor(x, y)`

Spawns a temple-style motor door.

```lua
function spawn_motordoor( x, y )
	EntityLoad( "data/entities/props/physics_templedoor2.xml", x, y )
end
```

#### `spawn_pressureplate(x, y)`

Spawns a temple pressure plate.

```lua
function spawn_pressureplate( x, y )
	EntityLoad( "data/entities/props/temple_pressure_plate.xml", x, y )
end
```

## Other Helper Functions (Unused or Placeholder)

The following functions are defined but appear to be either unused in this specific biome script or serve as placeholders for potential future implementation.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`

## `g_lamp` Table

This table defines parameters for spawning lamps, with a specific probability distribution.

```lua
g_lamp =
{
	total_prob = 0,
	-- add skullflys after this step
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,
		entity 	= "" -- Likely a placeholder or intended for dynamic assignment
	},
	{
		prob   		= 0.7,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics/lantern_small.xml"
	},
}
```

*   **`prob`**: The probability of spawning this specific lamp type.
*   **`min_count` / `max_count`**: The minimum and maximum number of entities to spawn.
*   **`entity`**: The XML path to the entity to spawn. The first entry with an empty string might indicate a special case or an unused slot.

### `spawn_lamp(x, y)`

A function to spawn lamps based on the `g_lamp` table.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x-5,y+1,0,0)
end
```