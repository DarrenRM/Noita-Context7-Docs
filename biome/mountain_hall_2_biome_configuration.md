---
title: Mountain Hall 2 Biome Configuration
category: biome
---

# Mountain Hall 2 Biome Configuration

This document outlines the configuration for the "Mountain Hall 2" biome in Noita, focusing on its integration into the game's biome system.

## Core Biome Setup

The `mountain_hall_2.lua` script registers and initializes the "Mountain Hall 2" biome. It relies on several helper functions and default biome logic.

### Initialization Function

The primary function responsible for setting up this biome is `init`.

```lua
function init( x, y, w, h )
	-- Loads the primary pixel scene for the biome.
	LoadPixelScene( "data/biome_impl/mountain/hall_2.png", "data/biome_impl/mountain/hall_2_visual.png", x, y, "data/biome_impl/mountain/hall_2_background.png", true )
	-- Loads an additional scene, likely for the lower portion of the biome.
	LoadPixelScene( "data/biome_impl/mountain/hall_2_bottom.png", "", x, y+512, "", true )
end
```

### Dependencies

This biome utilizes several external Lua files for its functionality:

*   `data/scripts/director_helpers.lua`: Provides helper functions for biome management and director logic.
*   `data/scripts/biomes/mountain/mountain.lua`: Contains general configurations and functions for mountain biomes.

### Registration

The biome is registered with the game's spawn system using a specific ID.

```lua
RegisterSpawnFunction( 0xffffeedd, "init" )
```

*   `0xffffeedd`: This is the unique identifier for the "Mountain Hall 2" biome within the game's internal system.
*   `"init"`: Specifies the function to be called when this biome is to be initialized.

## Key Attributes

*   **Biome ID:** `0xffffeedd`
*   **Initialization Script:** `data/scripts/biomes/mountain/mountain_hall_2.lua`
*   **Pixel Scene Files:**
    *   `data/biome_impl/mountain/hall_2.png` (Primary layout)
    *   `data/biome_impl/mountain/hall_2_visual.png` (Visual layer)
    *   `data/biome_impl/mountain/hall_2_background.png` (Background layer)
    *   `data/biome_impl/mountain/hall_2_bottom.png` (Additional scene, likely for lower areas)
*   **Dependencies:** `director_helpers.lua`, `mountain.lua`
*   **Purpose:** Defines a specific section or layout within the mountain biome environment.