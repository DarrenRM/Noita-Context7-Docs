---
title: Mountain Biome - Right Section
category: biome
---

---

# Mountain Biome - Right Section

This documentation describes the configuration for the right section of the Mountain biome in Noita, focusing on its procedural generation and visual elements.

## Core Generation

This section defines the primary functions and assets used to generate the right part of the Mountain biome.

### `init(x, y, w, h)` Function

This function is called during biome generation.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called with a specific identifier.
*   **`LoadPixelScene(...)`**: This is the core function for loading visual and structural data for the biome.
    *   **`data/biome_impl/mountain/right_bottom.png`**: Loads the pixel data for the lower part of the right section.
    *   **`data/biome_impl/mountain/right.png`**: Loads the primary pixel data for the right section.
    *   **`data/biome_impl/mountain/right_visual.png`**: Loads the visual overlay for the right section.
    *   **`data/biome_impl/mountain/right_background.png`**: Loads the background elements for the right section.

## Dependencies

The generation of this biome relies on several helper files.

*   **`dofile_once("data/scripts/director_helpers.lua")`**: Includes essential helper functions for biome and director logic.
*   **`dofile_once("data/scripts/biomes/mountain/mountain.lua")`**: Includes the base configuration for the Mountain biome.

## Constants

*   **`CHEST_LEVEL = 3`**: Defines the default level for chests within this biome.