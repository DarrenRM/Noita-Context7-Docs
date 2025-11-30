---
title: Mountain Lake Biome Pixel Scene
category: biome
---

# Mountain Lake Biome Pixel Scene

This document describes the pixel scene configuration for the Mountain Lake biome in Noita, focusing on AI-assisted modding.

## Pixel Scene Configuration

The `PixelScene` element defines a specific visual arrangement of pixels within the biome.

### Key Attributes

*   **`material_filename`**: Specifies the file containing the pixel data for this scene.
    *   `data/biome_impl/spliced/mountain_lake/0.plz`: This is the primary material file for the Mountain Lake biome's pixel scene.
*   **`pos_x`**: The X-coordinate where this pixel scene is placed.
    *   `2560`: Indicates the horizontal starting position.
*   **`pos_y`**: The Y-coordinate where this pixel scene is placed.
    *   `0`: Indicates the vertical starting position.
*   **`skip_biome_checks`**: A flag to bypass standard biome validation for this scene.
    *   `1`: Enables skipping biome checks.

### `mBufferedPixelScenes`

This element likely groups multiple buffered pixel scenes, allowing for optimized loading and rendering. The `PixelScene` within this group is the core definition for the Mountain Lake's visual layout.