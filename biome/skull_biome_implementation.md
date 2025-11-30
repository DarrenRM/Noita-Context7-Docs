---
title: Skull Biome Implementation
category: biome
---

# Skull Biome Implementation

This document details the implementation of the "Skull" biome within Noita, focusing on its visual and material definitions.

## Pixel Scenes

The `PixelScenes` element contains definitions for various visual and material configurations of the biome.

### Buffered Pixel Scenes

The `mBufferedPixelScenes` element holds pre-buffered pixel scene data for performance optimization.

#### Pixel Scene

The `PixelScene` element defines a specific instance or configuration of the biome's visual and material properties.

*   **`material_filename`**: Specifies the path to the file defining the biome's materials.
    *   Example: `data/biome_impl/spliced/skull/0.plz`
*   **`colors_filename`**: Specifies the path to the file defining the biome's color palette.
    *   Example: `data/biome_impl/spliced/skull/0_visual.plz`
*   **`pos_x`**: The X-coordinate for the scene's placement.
    *   Example: `14685`
*   **`pos_y`**: The Y-coordinate for the scene's placement.
    *   Example: `16198`
*   **`skip_biome_checks`**: A flag to skip biome checks for this scene.
    *   Example: `1` (true)
*   **`background_filename`**: (Empty in this example) Path to a background image file, if any.