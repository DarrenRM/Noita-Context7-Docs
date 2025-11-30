---
title: Mountain Hall 4 Biome
category: biome
---

---

# Mountain Hall 4 Biome

This document describes the configuration for the "Mountain Hall 4" biome in Noita, focusing on its implementation details for AI-assisted modding.

## Core Biome Loading

The `init` function is responsible for loading the visual and structural components of the biome.

### `init(x, y, w, h)`

*   **Purpose**: Initializes the biome at the specified coordinates.
*   **Key Actions**:
    *   Loads the primary pixel scene for the biome's layout and visual elements.
    *   Loads a secondary scene for the bottom portion of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/mountain/hall_4.png", "data/biome_impl/mountain/hall_4_visual.png", x, y, "data/biome_impl/mountain/hall_4_background.png", true )
	LoadPixelScene( "data/biome_impl/mountain/hall_4_bottom.png", "", x, y+512, "", true )
end
```

## Dependencies

This biome relies on several helper scripts for its functionality.

*   `data/scripts/director_helpers.lua`: Provides general director functionalities.
*   `data/scripts/biomes/mountain/mountain.lua`: Contains base mountain biome logic.

## Spawn Registration

The biome is registered to be spawned under specific conditions.

*   **Spawn Function**: `init`
*   **Spawn Condition**: `0xffffeedd` (This likely represents a specific biome ID or internal flag used by the game's director system.)

## Constants

*   `CHEST_LEVEL = 3`: Indicates the level at which chests are typically generated within this biome.