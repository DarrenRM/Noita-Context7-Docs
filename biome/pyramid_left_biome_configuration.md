---
title: Pyramid Left Biome Configuration
category: biome/
---

# Pyramid Left Biome Configuration

This document details the configuration for the "Pyramid Left" biome in Noita, focusing on its script-based generation and key elements.

## Core Biome Functionality

The `pyramid_left.lua` script defines the default behavior for this biome. It relies on helper functions from `director_helpers.lua` and `biome_scripts.lua` for its generation logic.

### Initialization

The `init` function is the primary entry point for this biome's generation. It's triggered by the `RegisterSpawnFunction` call.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/pyramid/left_bottom.png", "", x, y + 512, "", true )
	LoadPixelScene( "data/biome_impl/pyramid/left.png", "", x, y, "", true )
	LoadBackgroundSprite( "data/biome_impl/pyramid/left_background.png", x, y, 99.9 )
end
```

*   **`x`, `y`, `w`, `h`**: These parameters represent the position and dimensions of the biome area being generated.
*   **`LoadPixelScene`**: This function is used to load the visual layers of the biome.
    *   `data/biome_impl/pyramid/left_bottom.png`: Loads the lower section of the pyramid's visual representation.
    *   `data/biome_impl/pyramid/left.png`: Loads the main visual layer of the pyramid.
*   **`LoadBackgroundSprite`**: This function loads the background elements for the biome.
    *   `data/biome_impl/pyramid/left_background.png`: Specifies the background image for the Pyramid Left biome.
    *   `99.9`: This value likely represents the Z-order or depth of the background sprite.

## Spawn Functions (Default/Unused)

The following functions are defined but appear to be placeholders or default implementations that are not actively used for spawning specific entities or items within this particular biome script. Their presence suggests a standardized structure for biome scripts, allowing for extensibility.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `spawn_chest( x, y )`
*   `spawn_blood( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_save( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_persistent_teleport( x, y )`
*   `spawn_candles( x, y )`

## Constants

*   `CHEST_LEVEL = 3`: This constant likely defines a default chest tier or level associated with this biome, though it's not directly used in the provided `init` function.