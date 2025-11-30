---
title: Moon Biome Pixel Scenes
category: biome
---

# Moon Biome Pixel Scenes

This document details the pixel scene configurations for the Moon biome in Noita, as defined in `data/biome_impl/spliced/moon.xml`. Pixel scenes are used to define the visual and material composition of specific areas within a biome.

## PixelScene Configuration

The `PixelScene` element defines a specific visual and material layout for a portion of the biome.

### Key Attributes

*   **`background_filename`**: Specifies the path to the background image for this scene.
    *   Example: `data/biome_impl/spliced/moon/0_background.png`
*   **`colors_filename`**: Points to the file defining the color palette for the scene.
    *   Example: `data/biome_impl/spliced/moon/0_visual.plz`
*   **`material_filename`**: Indicates the file containing the material definitions for the scene's pixels.
    *   Example: `data/biome_impl/spliced/moon/0.plz`
*   **`pos_x`**: The X-coordinate position of the scene within the biome.
    *   Example: `13`
*   **`pos_y`**: The Y-coordinate position of the scene within the biome.
    *   Example: `-26104`
*   **`skip_biome_checks`**: A flag to potentially bypass standard biome generation checks for this scene.
    *   Example: `1` (true)

### mBufferedPixelScenes

This element acts as a container for multiple `PixelScene` definitions that are buffered for performance.