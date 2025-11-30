---
title: Lava Lake Pit Bottom Biome
category: biome
---

```

# Lava Lake Pit Bottom Biome

This document details the configuration for the "Lava Lake Pit Bottom" biome in Noita, focusing on its implementation through pixel scene splicing.

## Biome Splice Configuration

The `_lavalake_pit_bottom.bat` file orchestrates the creation of the Lava Lake Pit Bottom biome by splicing a pixel scene.

### Key Attributes

*   **`wizard_physics.exe -splice_pixel_scene`**: This command initiates the process of splicing a pixel scene.
*   **`data/biome_impl/spliced/lavalake_pit_bottom.png`**: This is the source image file containing the pixel data for the biome.
*   **`-x 2560`**: Specifies the width of the biome in pixels.
*   **`-y 3072`**: Specifies the height of the biome in pixels.

This biome is likely characterized by its fiery, molten environment, consistent with the "Lava Lake" theme. The splicing process allows for the efficient generation of large, complex biome areas from pre-defined pixel art.