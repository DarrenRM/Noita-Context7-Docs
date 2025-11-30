---
title: Mountain Right Entrance Biome Configuration
category: biome
---

# Mountain Right Entrance Biome Configuration

This document outlines the configuration for the "Mountain Right Entrance" biome in Noita, focusing on its script-based generation and key elements.

## Core Biome Setup

The `mountain_right_entrance.lua` script defines how this specific biome is initialized and populated within the game world. It relies on several helper functions and pre-defined biome data.

### Initialization Function

The primary function `init(x, y, w, h)` is responsible for loading the visual and structural components of the biome.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: This line registers the `init` function to be called when the game's director logic determines this biome should be spawned. The `0xffffeedd` likely represents a specific biome ID or tag.

### Pixel Scene Loading

The `init` function utilizes `LoadPixelScene` to place various pre-designed pixel art assets that form the biome's layout and appearance.

*   **`LoadPixelScene( "data/biome_impl/mountain/right_entrance_bottom.png", "", x, y+512, "", true )`**: Loads the bottom section of the right entrance.
*   **`LoadPixelScene( "data/biome_impl/mountain/right_bottom.png", "", x+512-192, y + 512, "", true )`**: Loads a segment of the general "right bottom" mountain area, offset from the main entrance.
*   **`LoadPixelScene( "data/biome_impl/mountain/right_entrance.png", "data/biome_impl/mountain/right_entrance_visual.png", x, y, "data/biome_impl/mountain/right_entrance_background.png", true )`**: This is the main loading call, placing the primary entrance structure, its visual details, and its background layer at the specified coordinates.

### Dependencies

The script includes essential helper files for biome generation.

*   **`dofile_once("data/scripts/director_helpers.lua")`**: Loads general helper functions used across various biomes for director logic.
*   **`dofile_once("data/scripts/biomes/mountain/mountain.lua")`**: Loads the core configuration and functions for the broader "mountain" biome type, providing a foundation for this specific entrance.

### Global Constants

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or rarity of chests that can spawn within this biome. A value of `3` suggests a mid-tier chest level.