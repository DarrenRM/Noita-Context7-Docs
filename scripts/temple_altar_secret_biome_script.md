---
title: Temple Altar Secret Biome Script
category: scripts
---

# Temple Altar Secret Biome Script

This script defines the behavior and entities for a secret area within the Temple biome, specifically focusing on an altar. It registers various spawn functions for different game elements and handles the loading of specific visual assets for this secret location.

## Key Spawn Functions

This script registers several functions to be called at specific points during gameplay, often triggered by unique identifiers.

*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Called for the initial setup of the biome.
*   `RegisterSpawnFunction( 0xff6d934c, "spawn_hp" )`: Spawns health pickups and coop respawn points.
*   `RegisterSpawnFunction( 0xff33934c, "spawn_shopitem" )`: Spawns a regular shop item.
*   `RegisterSpawnFunction( 0xff33935F, "spawn_cheap_shopitem" )`: Spawns a cheaper shop item.
*   `RegisterSpawnFunction( 0xff10822d, "spawn_workshop" )`: Spawns a workshop building.
*   `RegisterSpawnFunction( 0xff5a822d, "spawn_workshop_extra" )`: Spawns an additional workshop building that allows mods.
*   `RegisterSpawnFunction( 0xffFAABBA, "spawn_motordoor" )`: Spawns a temple motor door.
*   `RegisterSpawnFunction( 0xffFAABBB, "spawn_pressureplate" )`: Spawns a temple pressure plate.

## Core Initialization (`init`)

The `init` function is responsible for loading the visual elements of the secret altar area.

```lua
function init( x, y, w, h )
	-- LoadBackgroundSprite( "data/biome_impl/temple/wall_background.png", x, y - 30, 35 )
	LoadBackgroundSprite( "data/biome_impl/temple/wall_background.png", x, y - 30, 35 )
	
	LoadPixelScene( "data/biome_impl/temple/altar_top.png", "", x, y-40, "", true )
	LoadPixelScene( "data/biome_impl/temple/altar.png", "data/biome_impl/temple/altar_visual.png", x, y-40+300, "data/biome_impl/temple/altar_background_secret.png", true )
end
```

*   Loads a background sprite.
*   Loads the top part of the altar.
*   Loads the main altar structure, its visual overlay, and a specific background for the secret area.

## Entity Spawning Functions

These functions are called by their respective `RegisterSpawnFunction` calls to place specific entities in the game world.

### `spawn_hp`

Spawns a full health pickup and a coop respawn point.

```lua
function spawn_hp( x, y )
	EntityLoad( "data/entities/items/pickup/heart_fullhp_temple.xml", x, y )
	EntityLoad( "data/entities/buildings/coop_respawn.xml", x, y )
end
```

### `spawn_shopitem`

Spawns a shop item using a helper function.

```lua
function spawn_shopitem( x, y )
	-- EntityLoad( "data/entities/items/shop_item.xml", x, y )
	generate_shop_item( x, y, false )
end
```

### `spawn_cheap_shopitem`

Spawns a cheaper shop item using a helper function.

```lua
function spawn_cheap_shopitem( x, y )
	-- EntityLoad( "data/entities/items/shop_item.xml", x, y )
	generate_shop_item( x, y, true )
end
```

### `spawn_workshop`

Spawns a standard workshop building.

```lua
function spawn_workshop( x, y )
	EntityLoad( "data/entities/buildings/workshop.xml", x, y )
end
```

### `spawn_workshop_extra`

Spawns a workshop building that allows mods.

```lua
function spawn_workshop_extra( x, y )
	EntityLoad( "data/entities/buildings/workshop_allow_mods.xml", x, y )
end
```

### `spawn_motordoor`

Spawns a temple motor door.

```lua
function spawn_motordoor( x, y )
	EntityLoad( "data/entities/props/physics_templedoor2.xml", x, y )
end
```

### `spawn_pressureplate`

Spawns a temple pressure plate.

```lua
function spawn_pressureplate( x, y )
	EntityLoad( "data/entities/props/temple_pressure_plate.xml", x, y )
end
```

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, meaning they are placeholders or intended for use in other scripts.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`

## Lamp Spawning (`g_lamp`, `spawn_lamp`)

A table `g_lamp` is defined to specify properties for spawning lamps, though its `total_prob` is 0. The `spawn_lamp` function is also present but not registered for spawning.

```lua
g_lamp =
{
	total_prob = 0,
	-- add skullflys after this step
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,    
		entity 	= ""
	},
	{
		prob   		= 0.7,
		min_count	= 1,
		max_count	= 1,    
		entity 	= "data/entities/props/physics_lantern_small.xml"
	},
}

function spawn_lamp(x, y)
	spawn(g_lamp,x-5,y+1,0,0)
end
```