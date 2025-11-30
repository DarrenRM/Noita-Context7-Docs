---
title: Mountain Right Entrance 2 Biome
category: biome
---

# Mountain Right Entrance 2 Biome

This document describes the configuration for the "mountain_right_entrance_2" biome in Noita, intended for AI-assisted modding.

## Biome Registration

The biome is registered with the game using a specific color key and an initialization function.

```lua
RegisterSpawnFunction( 0xffffeedd, "init" )
```

*   **`0xffffeedd`**: This is the color key used to identify and spawn this biome.
*   **`"init"`**: This is the name of the function that will be called to initialize the biome.

## Initialization Function (`init`)

The `init` function is responsible for loading the visual and pixel data for the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/mountain/right_entrance_2.png", "data/biome_impl/mountain/right_entrance_2_visual.png", x, y, "", true )
end
```

*   **`x`, `y`, `w`, `h`**: These parameters represent the position and dimensions where the biome will be loaded.
*   **`LoadPixelScene(...)`**: This function loads the biome's visual and collision data.
    *   `"data/biome_impl/mountain/right_entrance_2.png"`: The primary pixel data file for the biome.
    *   `"data/biome_impl/mountain/right_entrance_2_visual.png"`: The visual layer for the biome.
    *   `""`: An empty string, likely for optional overlay data.
    *   `true`: A boolean flag, potentially indicating whether to use collision data.

## Dependencies

This biome relies on several helper scripts for its functionality.

```lua
CHEST_LEVEL = 3
dofile_once("data/scripts/director_helpers.lua")
dofile_once("data/scripts/biomes/mountain/mountain.lua")
```

*   **`CHEST_LEVEL = 3`**: Sets a global variable related to chest spawning difficulty or type within this biome.
*   **`dofile_once("data/scripts/director_helpers.lua")`**: Loads essential director helper functions.
*   **`dofile_once("data/scripts/biomes/mountain/mountain.lua")`**: Loads general mountain biome functionalities, which might include default behaviors or shared assets.