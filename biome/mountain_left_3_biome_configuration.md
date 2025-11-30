---
title: Mountain Left 3 Biome Configuration
category: biome
---

# Mountain Left 3 Biome Configuration

This document outlines the configuration for the "mountain_left_3" biome in Noita, focusing on its core setup and loading mechanisms.

## Biome Registration

The `mountain_left_3` biome is registered with the game using a specific color key, indicating its association with certain spawn events or conditions.

### Spawn Function Registration

```lua
RegisterSpawnFunction( 0xffffeedd, "init" )
```

*   **Color Key:** `0xffffeedd` - This hexadecimal color value is used to identify and trigger the `init` function when this specific biome is encountered.
*   **Function Name:** `"init"` - The primary function responsible for initializing this biome.

## Biome Initialization

The `init` function is called when the game determines that the `mountain_left_3` biome should be loaded. It handles the loading of the biome's visual and pixel data.

### `init` Function

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/mountain/left_3.png", "data/biome_impl/mountain/left_3_visual.png", x, y, "", true )
end
```

*   **Parameters:**
    *   `x`, `y`: The starting coordinates for loading the biome.
    *   `w`, `h`: The width and height of the area to load.
*   **`LoadPixelScene`:** This core function is used to load the biome's geometry and visual representation.
    *   **Pixel Data:** `"data/biome_impl/mountain/left_3.png"` - The file containing the pixel-based definition of the biome's structure.
    *   **Visual Data:** `"data/biome_impl/mountain/left_3_visual.png"` - The file containing the visual layer for the biome.
    *   **Positioning:** `x`, `y` are used to place the loaded scene.
    *   **Empty String (`""`):** Likely a placeholder or unused parameter for additional scene data.
    *   **`true`:** Indicates that the scene should be loaded with its associated physics or collision data.

## Dependencies

This biome configuration relies on several helper files for its functionality.

### `dofile_once` Calls

```lua
dofile_once("data/scripts/director_helpers.lua")
dofile_once("data/scripts/biomes/mountain/mountain.lua")
```

*   **`director_helpers.lua`:** Provides general utility functions for managing game directors and biome spawning.
*   **`mountain.lua`:** Contains shared logic and definitions specific to mountain biomes, ensuring consistency across different mountain variants.

## Global Constants

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or quality of chests that can spawn within this biome. A value of `3` suggests a mid-to-high tier of loot.