---
title: Essenceroom Air Biome Script
category: scripts/biome
---

# Essenceroom Air Biome Script

This script defines the behavior and entity spawning for the "Essenceroom Air" biome in Noita. It focuses on loading the visual elements of the biome and spawning specific "air essence" pickups.

## Core Functionality

### Initialization (`init`)

This function is called when the biome is first loaded. It's responsible for setting up the visual and structural components of the Essenceroom Air.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/essenceroom.png", "data/biome_impl/essenceroom_visual.png", x, y, "data/biome_impl/essenceroom_background_diamond.png", true )
end
```

*   **`LoadPixelScene`**: This is the primary function used to load the visual assets for the biome.
    *   `"data/biome_impl/essenceroom.png"`: The base pixel data for the biome's layout.
    *   `"data/biome_impl/essenceroom_visual.png"`: The visual layer that overlays the base data.
    *   `x, y`: The coordinates where the scene will be loaded.
    *   `"data/biome_impl/essenceroom_background_diamond.png"`: A background element specific to this biome.
    *   `true`: Likely indicates whether to use collision data from the pixel scene.

### Entity Spawning (`spawn_essence`)

This function is triggered to spawn specific entities within the biome.

```lua
function spawn_essence(x, y)
	EntityLoad( "data/entities/items/pickup/essence_air.xml", x, y )
end
```

*   **`EntityLoad`**: This function loads an entity from its XML definition.
    *   `"data/entities/items/pickup/essence_air.xml"`: The specific entity being loaded, which is the "air essence" pickup.
    *   `x, y`: The coordinates where the "air essence" will be spawned.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or intended for future expansion.

*   `spawn_small_enemies( x, y )`
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
*   `spawn_wands( x, y )`
*   `spawn_orb(x, y)`

## Registration

The script registers two spawn functions to be called by the game's director system.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called at a specific point during biome generation (identified by the hex code `0xffffeedd`).
*   **`RegisterSpawnFunction( 0xff31d0b4, "spawn_essence" )`**: Registers the `spawn_essence` function to be called at another point (identified by `0xff31d0b4`), likely after the biome structure is in place.