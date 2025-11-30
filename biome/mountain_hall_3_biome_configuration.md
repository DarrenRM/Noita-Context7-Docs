---
title: Mountain Hall 3 Biome Configuration
category: biome
---

# Mountain Hall 3 Biome Configuration

This document details the configuration for the "Mountain Hall 3" biome in Noita, focusing on its implementation for AI-assisted modding.

## Core Biome Setup

The `mountain_hall_3.lua` script defines the foundational elements and loading procedures for this specific biome.

### Initialization Function

The `init` function is the primary entry point for loading the biome's visual and structural components.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/mountain/hall_3_long.png", "data/biome_impl/mountain/hall_3_long_visual.png", x, y, "data/biome_impl/mountain/hall_3_long_background.png", true )
	LoadPixelScene( "data/biome_impl/mountain/hall_3_top.png", "", x, y-512, "", true )
	LoadPixelScene( "data/biome_impl/mountain/hall_3_bottom.png", "", x, y+512, "", true )
	LoadPixelScene( "data/biome_impl/mountain/inside_bottom_right.png", "", x + 512, y - 512, "", true )
	LoadPixelScene( "data/biome_impl/mountain/inside_bottom_left.png", "", x, y - 512, "", true )
	LoadPixelScene( "data/biome_impl/mountain/inside_top_right.png", "", x, y - 1024, "", true )
	LoadPixelScene( "data/biome_impl/mountain/inside_top_left.png", "", x, y - 1024, "", true )
end
```

### Key `LoadPixelScene` Parameters:

*   **`filepath`**: The path to the `.png` file defining the biome's structure or visuals.
*   **`visual_filepath`**: (Optional) Path to a separate file for visual layering.
*   **`background_filepath`**: (Optional) Path to a background image.
*   **`x`, `y`**: The coordinates where the scene will be loaded.
*   **`offset_x`, `offset_y`**: Adjustments to the loading position.
*   **`is_background`**: Boolean indicating if the scene is a background element.

### Loaded Pixel Scenes:

The following pixel scenes are loaded to construct the "Mountain Hall 3" biome:

| Scene File                                     | Visual File | Background File | X Offset | Y Offset | Is Background |
| :--------------------------------------------- | :---------- | :-------------- | :------- | :------- | :------------ |
| `data/biome_impl/mountain/hall_3_long.png`     | `hall_3_long_visual.png` | `hall_3_long_background.png` | `x`      | `y`      | `true`        |
| `data/biome_impl/mountain/hall_3_top.png`      |             |                 | `x`      | `y-512`  | `true`        |
| `data/biome_impl/mountain/hall_3_bottom.png`   |             |                 | `x`      | `y+512`  | `true`        |
| `data/biome_impl/mountain/inside_bottom_right.png` |             |                 | `x+512`  | `y-512`  | `true`        |
| `data/biome_impl/mountain/inside_bottom_left.png`  |             |                 | `x`      | `y-512`  | `true`        |
| `data/biome_impl/mountain/inside_top_right.png`    |             |                 | `x`      | `y-1024` | `true`        |
| `data/biome_impl/mountain/inside_top_left.png`     |             |                 | `x`      | `y-1024` | `true`        |

## Dependencies and Global Variables

This biome relies on several external scripts and global configurations.

### Required Scripts:

*   `data/scripts/director_helpers.lua`: Provides utility functions for game direction and spawning.
*   `data/scripts/biomes/mountain/mountain.lua`: Likely contains shared logic or definitions for mountain biomes.

### Global Variables:

*   `CHEST_LEVEL = 3`: Indicates the difficulty or tier for chests spawned within this biome.

## Spawn Functions

The `RegisterSpawnFunction` call ensures that the `init` function is executed when this biome is selected by the game director.

```lua
RegisterSpawnFunction( 0xffffeedd, "init" )
```

*   `0xffffeedd`: A unique identifier or hash associated with this biome's spawn logic.
*   `"init"`: The name of the function to call upon biome registration.

## Unused Functionality

The `spawn_persistent_teleport` function is present but commented out, indicating it's not currently used for this biome.

```lua
function spawn_persistent_teleport(x, y)
	--spawn(g_persistent_teleport,x,y,0,0)
end
```