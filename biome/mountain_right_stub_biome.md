---
title: Mountain Right Stub Biome
category: biome
---

# Mountain Right Stub Biome

This file defines a stub biome for the right side of the mountain. It serves as a fallback or a placeholder when a more specific biome isn't found.

## Core Functionality

*   **`CHEST_LEVEL`**: Set to `3`, indicating the general chest tier for this biome.
*   **`dofile_once`**: Includes essential helper scripts for director logic and the main mountain biome definition.
*   **`RegisterSpawnFunction`**: Registers the `init` function to be called during biome initialization.

## Initialization (`init` function)

The `init` function is responsible for loading the visual elements of the biome.

### Key Parameters

*   `x`, `y`: Coordinates for the biome's placement.
*   `w`, `h`: Dimensions of the biome area.

### Loading Visuals

*   **`LoadPixelScene`**: This function is used to load the biome's visual components.
    *   `"data/biome_impl/mountain/right_stub.png"`: The primary pixel scene for the biome.
    *   `""`: An empty string for a secondary pixel scene (not used here).
    *   `x-38`, `y`: Offset for the primary pixel scene.
    *   `"data/biome_impl/mountain/right_stub_background.png"`: The background image for the biome.
    *   `true`: Indicates that the background should be drawn.