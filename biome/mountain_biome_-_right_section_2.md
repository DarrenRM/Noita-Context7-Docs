---
title: Mountain Biome - Right Section 2
category: biome
---

---

# Mountain Biome - Right Section 2

This script defines a specific section of the Mountain biome in Noita, focusing on its right-hand side. It leverages existing biome functions and loads specific pixel scenes to construct the environment.

## Key Functions

### `init(x, y, w, h)`

This is the primary initialization function for this biome section. It's responsible for loading the visual elements that make up the environment.

*   **`LoadPixelScene(filepath, material_file, offset_x, offset_y, background_filepath, is_foreground)`**: This function is used to load visual data for the biome.

    *   **`data/biome_impl/mountain/right_bottom.png`**: Loads the pixel data for the lower portion of this right-hand section.
    *   **`data/biome_impl/mountain/right_2.png`**: Loads the primary pixel data for this specific right-hand section.
    *   **`data/biome_impl/mountain/right_background.png`**: Loads the background elements for this section.

## Constants

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or frequency of chests that can spawn within this biome section.

## Dependencies

*   **`dofile_once("data/scripts/director_helpers.lua")`**: Imports helper functions for managing game directors and spawns.
*   **`dofile_once("data/scripts/biomes/mountain/mountain.lua")`**: Imports core functions and definitions for the Mountain biome.

## Registration

*   **`RegisterSpawnFunction(0xffffeedd, "init")`**: Registers the `init` function to be called when the game needs to spawn this specific biome section, identified by the color `0xffffeedd`.