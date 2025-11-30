---
title: Laboratory Biome Pixel Scenes
category: biome
---

# Laboratory Biome Pixel Scenes

This document details the configuration for pixel scenes within the Laboratory biome in Noita, as defined in `_pixel_scenes_laboratory.xml`. Pixel scenes are pre-defined arrangements of materials and entities that can be placed within biomes.

## Pixel Scene Files

This section lists external XML files that contribute spliced pixel scenes to the Laboratory biome.

*   `data/biome_impl/spliced/mountain_lake.xml`: Integrates scenes from the Mountain Lake biome.

## Buffered Pixel Scenes

These are directly defined pixel scenes that are loaded and placed within the Laboratory biome.

### `range.png` Scene

This scene is defined by the `range.png` material file.

*   **`material_filename`**: `data/biome_impl/laboratory/range.png`
    *   This PNG file dictates the material composition and layout of the scene.
*   **`pos_x`**: `0`
    *   The horizontal position where the scene is anchored.
*   **`pos_y`**: `-386`
    *   The vertical position where the scene is anchored.
*   **`clean_area_before`**: `1`
    *   Indicates that the area should be cleared of existing materials before placing this scene.
*   **`skip_biome_checks`**: `1`
    *   Bypasses standard biome validation for placement.
*   **`skip_edge_textures`**: `0`
    *   Does not skip the placement of edge textures for this scene.
*   **`background_filename`**: `""`
    *   No specific background file is associated with this scene.
*   **`colors_filename`**: `""`
    *   No specific color palette file is associated with this scene.