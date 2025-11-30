---
title: Mountain Left Biome Configuration
category: biome
---

# Mountain Left Biome Configuration

This document outlines the configuration for the "Mountain Left" biome in Noita, focusing on its initialization and visual setup.

## Initialization

The `init` function is responsible for loading the visual and structural elements of the biome.

### Key Functions

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called during biome generation. The `0xffffeedd` likely represents a unique identifier or seed for this biome.
*   **`dofile_once(...)`**: Includes essential helper scripts for director logic and the general mountain biome.

### `init( x, y, w, h )` Function

This function is called when the "Mountain Left" biome is to be generated at a specific position (`x`, `y`) with dimensions (`w`, `h`).

*   **`LoadPixelScene( "data/biome_impl/mountain/left_bottom.png", "", x, y + 512, "", true )`**: Loads the bottom portion of the biome's pixel scene.
    *   `pixel_scene_path`: `data/biome_impl/mountain/left_bottom.png`
    *   `visual_scene_path`: `""` (no separate visual layer for this part)
    *   `x`, `y`: Position for loading. `y + 512` suggests it's placed below the main scene.
    *   `background_path`: `""` (no background for this part)
    *   `is_unique`: `true` (likely means this scene is only loaded once)

*   **`LoadPixelScene( "data/biome_impl/mountain/left.png", "data/biome_impl/mountain/left_visual.png", x, y, "data/biome_impl/mountain/left_background.png", true )`**: Loads the main visual and structural components of the biome.
    *   `pixel_scene_path`: `data/biome_impl/mountain/left.png` (defines the physical layout)
    *   `visual_scene_path`: `data/biome_impl/mountain/left_visual.png` (defines the visual appearance)
    *   `x`, `y`: Position for loading.
    *   `background_path`: `data/biome_impl/mountain/left_background.png` (defines the background layer)
    *   `is_unique`: `true`

## Constants

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or frequency of chests that can spawn within this biome. A value of `3` suggests a mid-tier level for loot.