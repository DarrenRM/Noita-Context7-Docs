---
title: Skull in Desert Biome Visuals
category: biome
---

# Skull in Desert Biome Visuals

This document describes the visual components of the "Skull in Desert" biome in Noita, as defined in `skull_in_desert.xml`.

## Pixel Scenes

The `PixelScenes` element defines the visual layers and their placement for this biome.

### Buffered Pixel Scenes

The `mBufferedPixelScenes` element contains individual `PixelScene` definitions.

#### PixelScene

This element defines a specific visual layer for the biome.

*   **`material_filename`**: Specifies the PNG file containing the material data for this layer.
    *   Example: `data/biome_impl/spliced/skull_in_desert/1.png`
*   **`colors_filename`**: Specifies the PNG file containing the color data for this layer.
    *   Example: `data/biome_impl/spliced/skull_in_desert/1_visual.png`
*   **`pos_x`**: The X-coordinate for the placement of this scene.
    *   Example: `7100`
*   **`pos_y`**: The Y-coordinate for the placement of this scene.
    *   Example: `-100`
*   **`skip_biome_checks`**: A flag to indicate if biome checks should be skipped for this scene. `1` means skip.
    *   Example: `1`
*   **`background_filename`**: (Optional) Specifies a background image file. This is empty in this example.

This `PixelScene` likely represents a specific visual chunk or element within the larger "Skull in Desert" biome, contributing to its overall appearance and material composition.