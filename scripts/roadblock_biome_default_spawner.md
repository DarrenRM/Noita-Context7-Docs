---
title: Roadblock Biome Default Spawner
category: scripts/
---

# Roadblock Biome Default Spawner

This script defines the default spawning behavior for the "roadblock" biome in Noita. It acts as a fallback when more specific biome configurations are not found.

## Key Functions

### `RegisterSpawnFunction`

Registers the `init` function to be called for biome spawning.

```lua
RegisterSpawnFunction( 0xffffeedd, "init" )
```

### `init`

This is the primary function called to initialize the roadblock biome. It loads a specific pixel scene to define the biome's layout and visual elements.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/roadblock.png", "", x, y, "", true )
end
```

## Helper Functions (Unused/Placeholder)

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or intended for future expansion.

### `spawn_small_enemies`

This function is intended to spawn small enemies within a given area. Currently, it spawns 10 `acidshooter` entities in a small radius.

```lua
function spawn_small_enemies( x, y )
	for i=1,10 do
		EntityLoad( "data/entities/animals/acidshooter.xml", x+(-5+i)*16, y+(-5+i)*16)
	end
end
```

### Placeholder Spawn Functions

These functions are defined but have no implementation, indicating they are not used in this specific biome's default setup.

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

## Dependencies

This script relies on external helper functions and definitions from other Noita scripts.

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`

## Constants

*   `CHEST_LEVEL = 3`: This constant likely influences the type or rarity of chests that can spawn in this biome, though it's not directly used in the provided `init` function.